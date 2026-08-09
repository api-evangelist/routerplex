---
name: Generate an image through RouterPlex
description: >-
  Run an OpenAI-compatible image generation against RouterPlex, choose a supported
  size and quality, and handle the base64 response and the failure modes that cost
  money.
api: openapi/routerplex-inference-openapi.json
operations:
  - createImageGeneration
  - listModels
generated: '2026-08-09'
method: generated
source: >-
  openapi/routerplex-inference-openapi.json, https://docs.routerplex.com/images,
  errors/routerplex-problem-types.yml
---

# Generate an image through RouterPlex

## 1. Confirm the image model is on this key — `listModels`

`GET /v1/models` with your key. Image generation needs an image-capable model; the
catalog exposes `gpt-image-2` (OpenAI). If the key's allowlist excludes it, the call
in step 2 fails — check first rather than paying for a rejected request.

## 2. Generate — `createImageGeneration`

```
POST https://api.routerplex.com/v1/images/generations
Authorization: Bearer $ROUTERPLEX_API_KEY
Content-Type: application/json

{
  "model": "gpt-image-2",
  "prompt": "...",
  "size": "<a size the model supports>",
  "quality": "<a quality the model supports>"
}
```

Required: `model`, `prompt` (min length 1). `size` and `quality` are optional strings
and are **validated against the selected model** — the spec says only "an image size
supported by the selected model." Passing a size the model does not support returns
`400`, and `400` is the one failure code the other RouterPlex routes do not declare.

## 3. Read the response

`200` returns image data as **base64** in the response body. There is no hosted image
URL and no retention guarantee — persist the bytes yourself on receipt. Note the
50 MB request-body ceiling if you are round-tripping base64 input.

## 4. Failure handling

| Status | Retry? | Cause |
|---|---|---|
| `400` | **No** | Malformed request, **unsupported image option**, or insufficient prepaid balance. |
| `401` | **No** | Missing or invalid API key. |
| `429` | **Conditional** | Rate limit → back off. Reached spend limit → stop. |
| `5xx` | Yes | Upstream provider. |

Image generation is billable per request and there is no idempotency key. A retried
generation is a second charge for a different image — never retry automatically on
`400`. Cap the spend with a per-key lifetime budget before running a batch.
