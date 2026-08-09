---
name: Select a RouterPlex model and call it
description: >-
  Discover which models a RouterPlex key can use, pick one on price and context,
  and run an OpenAI-compatible chat completion — with the spend and retry rules
  that keep an agent from burning a balance.
api: openapi/routerplex-inference-openapi.json
operations:
  - listModels
  - createChatCompletion
generated: '2026-08-09'
method: generated
source: >-
  openapi/routerplex-inference-openapi.json, conventions/routerplex-conventions.yml,
  errors/routerplex-problem-types.yml, rate-limits/routerplex-rate-limits.yml
---

# Select a RouterPlex model and call it

RouterPlex is an OpenAI- and Anthropic-compatible gateway. Base URL:
`https://api.routerplex.com/v1`. One API key, one prepaid balance, ~39 models.

## Before you call anything

Shop the catalog for free. The MCP server at `https://routerplex.com/mcp` is
anonymous and read-only, and never performs inference — use `routerplex_list_models`
or `routerplex_find_models` to compare price, context window and vision support with
no key and no charge. See `mcp/routerplex-mcp.yml`.

## 1. Confirm what this key may use — `listModels`

```
GET https://api.routerplex.com/v1/models
Authorization: Bearer $ROUTERPLEX_API_KEY
```

`listModels` returns only the models available to the **authenticated key**, honoring
that key's model allowlist. This is not the same as the public catalog — if a model
you expect is missing, the key's allowlist excludes it, not the platform.

- `200` — model IDs and metadata.
- `401` — the key is missing or invalid. Do not retry; fix the key.

## 2. Run the completion — `createChatCompletion`

```
POST https://api.routerplex.com/v1/chat/completions
Authorization: Bearer $ROUTERPLEX_API_KEY
Content-Type: application/json

{ "model": "<id from step 1>", "messages": [ {"role":"user","content":"..."} ], "stream": false }
```

Required: `model`, `messages` (min 1 item). `stream` defaults to `false`. The request
schema is `additionalProperties: true`, so vendor-specific parameters pass through to
the upstream provider — but RouterPlex does not validate them, and an unsupported
parameter comes back as a `400`.

Set `stream: true` for server-sent events. Streams stay open a maximum of **10 minutes**;
budget long generations accordingly.

## 3. Handle the response codes correctly

This is the part agents get wrong. From `errors/routerplex-problem-types.yml`:

| Status | Retry? | What to do |
|---|---|---|
| `400` | **No** | Malformed request, unsupported parameter, **or insufficient prepaid balance**. Read `error.message`. A retry cannot restore a zero balance. |
| `401` | **No** | Fix the key. |
| `429` | **Conditional** | Rate limit → back off and retry. Reached spend limit → **stop**. A retry cannot raise a hard key budget. Read `error.code` to tell them apart. |
| `5xx` | **Yes** | Upstream model vendor issue. Retry with backoff. |

Errors use the OpenAI envelope, not `application/problem+json`:

```json
{"error": {"message": "...", "type": "invalid_request_error", "code": "..."}}
```

No `RateLimit`/`Retry-After` headers are published — implement your own exponential
backoff. The edge limit is **60 requests/second per IP**.

## 4. There is no idempotency key

`createChatCompletion` is **billable and non-idempotent**. RouterPlex documents no
idempotency header, and none exists in the OpenAPI. A blind retry is a second charge.
Dedupe client-side: hold a request ID of your own, and never retry a `400` or a
spend-limit `429`.

## 5. Contain the spend before you start a long run

Give this agent its **own** API key with a hard lifetime budget and a model allowlist
(dashboard → keys). RouterPlex's own guidance: "an agent gone wild can't drain your
whole balance." The prepaid balance floors at `$0` and never goes negative. See
`sandbox/routerplex-sandbox.yml` — there is no test mode, so budget caps are the
only safety rail.
