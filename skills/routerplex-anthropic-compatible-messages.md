---
name: Call any RouterPlex model through the Anthropic Messages format
description: >-
  Use the Anthropic SDK or /v1/messages wire format against RouterPlex to reach any
  model in the catalog — including non-Claude models — and read the Anthropic SSE
  event stream it returns.
api: openapi/routerplex-inference-openapi.json
operations:
  - createMessage
  - listModels
generated: '2026-08-09'
method: generated
source: >-
  openapi/routerplex-inference-openapi.json, https://docs.routerplex.com/anthropic-messages,
  conventions/routerplex-conventions.yml, errors/routerplex-problem-types.yml
---

# Call any RouterPlex model through the Anthropic Messages format

The point of this route: an Anthropic-shaped client — the Anthropic SDK, Claude Code,
any `/v1/messages` caller — can reach **every** model RouterPlex fronts, not just
Claude. RouterPlex translates both the request and the event stream.

## 1. Authenticate

`createMessage` accepts **either** header:

```
x-api-key: sk-...              # Anthropic-compatible clients
Authorization: Bearer sk-...   # OpenAI-compatible clients
```

Both work on `/v1/messages`. Use whichever your SDK emits by default — do not send both.

## 2. Pick a model — `listModels`

`GET /v1/models` returns the IDs this key may use. Model IDs are RouterPlex catalog
IDs (e.g. `claude-opus-5`, `gpt-5-6-terra`, `gemini-3-1-pro`), not Anthropic IDs. Do
not assume an Anthropic model string will resolve.

## 3. Send the message — `createMessage`

```
POST https://api.routerplex.com/v1/messages
x-api-key: $ROUTERPLEX_API_KEY
Content-Type: application/json

{
  "model": "<id from step 2>",
  "messages": [ {"role":"user","content":"..."} ],
  "max_tokens": 1024,
  "stream": false
}
```

Required by the spec: `model`, `messages` (min 1). `max_tokens` is an integer ≥ 1 and
is what Anthropic clients will send. The schema is `additionalProperties: true`, so
other Anthropic fields pass through.

## 4. Streaming returns Anthropic events for every model

With `stream: true`, RouterPlex emits Anthropic SSE event names — `message_start`,
`content_block_delta`, `message_stop` — **including when the selected model is not a
Claude model**. An Anthropic SDK stream handler works unmodified against a Gemini or
GPT model. Streams close after 10 minutes.

## 5. Errors

Same envelope and same retry rules as every other route
(`errors/routerplex-problem-types.yml`): `401` fix the key, `400` fix the request or
top up, `429` back off for a rate limit but **stop** for a reached spend limit, `5xx`
retry. Errors come back in the OpenAI shape `{"error":{"message","type","code"}}` —
not the Anthropic error shape — so error handling is the one place the compatibility
is not literal. Handle it.

## 6. Which format should you use?

Prefer Chat Completions (`createChatCompletion`) unless your client requires the
Anthropic format. Use `createCodexResponse` (`POST /v1/responses`) only for Codex
custom model providers. All three are billable and none are idempotent — see
`conventions/routerplex-conventions.yml`.
