# RouterPlex (routerplex)

RouterPlex is an OpenAI- and Anthropic-compatible AI gateway that fronts 39 chat and image models from 14 vendors — OpenAI, Anthropic, Google, DeepSeek, Moonshot, Alibaba, MiniMax, Zhipu, xAI and others — behind one API key and one prepaid balance, at vendor list prices with no markup and no top-up fee. It exposes OpenAI Chat Completions, the OpenAI Responses route for Codex, Anthropic Messages, image generation and a model catalog on a single v1 REST surface, so the official OpenAI and Anthropic SDKs work unmodified with only a base URL change. Per-key hard spend budgets, model allowlists and optional RPM/TPM limits are the containment model for autonomous agents. RouterPlex also runs an anonymous read-only MCP server for model discovery and publishes an RFC 9727 API catalog, an OpenAPI 3.1 description, llms.txt and Markdown pricing and benchmark companions.

**APIs.json:** [https://routerplex.apievangelist.com/apis.yml](https://routerplex.apievangelist.com/apis.yml)

## Tags

- llm
- ai
- ai-gateway
- inference
- model-router
- openai-compatible
- anthropic-compatible
- claude
- gpt
- gemini
- api-gateway
- agent-infrastructure
- developer-tools
- mcp
- llmops

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-08-09

## APIs

### RouterPlex Chat API

The Chat API from RouterPlex — 1 operation(s) for chat.

- **Human URL:** [https://docs.routerplex.com](https://docs.routerplex.com)
- **Base URL:** `https://api.routerplex.com/v1`

#### Tags

- Chat

#### Properties

- [OpenAPI](openapi/routerplex-chat-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/routerplex-chat-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/routerplex-chat-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.routerplex.com)
- [API Reference](https://docs.routerplex.com/chat-completions)
- [Getting Started](https://docs.routerplex.com/quickstart)
- [Authentication](https://docs.routerplex.com/authentication)
- [Error Catalog](https://docs.routerplex.com/errors)
- [L L M S Txt](https://routerplex.com/llms.txt)
- [L L M S Txt](https://docs.routerplex.com/llms-full.txt)

### RouterPlex Images API

The Images API from RouterPlex — 1 operation(s) for images.

- **Human URL:** [https://docs.routerplex.com](https://docs.routerplex.com)
- **Base URL:** `https://api.routerplex.com/v1`

#### Tags

- Images

#### Properties

- [OpenAPI](openapi/routerplex-images-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/routerplex-images-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/routerplex-images-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.routerplex.com)
- [API Reference](https://docs.routerplex.com/chat-completions)
- [Getting Started](https://docs.routerplex.com/quickstart)
- [Authentication](https://docs.routerplex.com/authentication)
- [Error Catalog](https://docs.routerplex.com/errors)
- [L L M S Txt](https://routerplex.com/llms.txt)
- [L L M S Txt](https://docs.routerplex.com/llms-full.txt)

### RouterPlex Messages API

The Messages API from RouterPlex — 1 operation(s) for messages.

- **Human URL:** [https://docs.routerplex.com](https://docs.routerplex.com)
- **Base URL:** `https://api.routerplex.com/v1`

#### Tags

- Messages

#### Properties

- [OpenAPI](openapi/routerplex-messages-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/routerplex-messages-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/routerplex-messages-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.routerplex.com)
- [API Reference](https://docs.routerplex.com/chat-completions)
- [Getting Started](https://docs.routerplex.com/quickstart)
- [Authentication](https://docs.routerplex.com/authentication)
- [Error Catalog](https://docs.routerplex.com/errors)
- [L L M S Txt](https://routerplex.com/llms.txt)
- [L L M S Txt](https://docs.routerplex.com/llms-full.txt)

### RouterPlex Models API

The Models API from RouterPlex — 1 operation(s) for models.

- **Human URL:** [https://docs.routerplex.com](https://docs.routerplex.com)
- **Base URL:** `https://api.routerplex.com/v1`

#### Tags

- Models

#### Properties

- [OpenAPI](openapi/routerplex-models-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/routerplex-models-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/routerplex-models-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.routerplex.com)
- [API Reference](https://docs.routerplex.com/chat-completions)
- [Getting Started](https://docs.routerplex.com/quickstart)
- [Authentication](https://docs.routerplex.com/authentication)
- [Error Catalog](https://docs.routerplex.com/errors)
- [L L M S Txt](https://routerplex.com/llms.txt)
- [L L M S Txt](https://docs.routerplex.com/llms-full.txt)

### RouterPlex Responses API

The Responses API from RouterPlex — 1 operation(s) for responses.

- **Human URL:** [https://docs.routerplex.com](https://docs.routerplex.com)
- **Base URL:** `https://api.routerplex.com/v1`

#### Tags

- Responses

#### Properties

- [OpenAPI](openapi/routerplex-responses-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/routerplex-responses-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/routerplex-responses-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.routerplex.com)
- [API Reference](https://docs.routerplex.com/chat-completions)
- [Getting Started](https://docs.routerplex.com/quickstart)
- [Authentication](https://docs.routerplex.com/authentication)
- [Error Catalog](https://docs.routerplex.com/errors)
- [L L M S Txt](https://routerplex.com/llms.txt)
- [L L M S Txt](https://docs.routerplex.com/llms-full.txt)

## Common Properties

- [Overlay](overlays/routerplex-inference-overlay.yaml)
- [Agentic Access](agentic-access/routerplex-agentic-access.yml)
- [Domain Security](security/routerplex-domain-security.yml)
- [Authentication](authentication/routerplex-authentication.yml)
- [Website](https://routerplex.com)
- [Developer Portal](https://docs.routerplex.com)
- [Documentation](https://docs.routerplex.com)
- [API Reference](https://docs.routerplex.com/chat-completions)
- [Getting Started](https://docs.routerplex.com/quickstart)
- [Support](mailto:support@routerplex.com)
- [Support](https://t.me/RouterPlex)
- [Blog](https://routerplex.com/blog)
- [Blog R S S](https://routerplex.com/rss.xml)
- [GitHub Organization](https://github.com/RouterPlex)
- [Pricing](https://routerplex.com/pricing)
- [Sign Up](https://routerplex.com/sign-up)
- [Login](https://routerplex.com/sign-in)
- [Terms of Service](https://routerplex.com/terms)
- [Privacy Policy](https://routerplex.com/privacy)
- [M C P Server](mcp/routerplex-mcp.yml)
- [Tool Crosswalk](mcp/routerplex-tool-crosswalk.yml)
- [Agent Skill](skills/_index.yml)
- [L L Ms Txt](llms/routerplex-llms.txt)
- [Well Known](well-known/routerplex-well-known.yml)
- [A P I Catalog](https://routerplex.com/.well-known/api-catalog)
- [Content Signal](https://routerplex.com/robots.txt)
- [Conformance](conformance/routerplex-conformance.yml)
- [Error Catalog](errors/routerplex-problem-types.yml)
- [Lifecycle](lifecycle/routerplex-lifecycle.yml)
- [Conventions](conventions/routerplex-conventions.yml)
- [Rate Limits](rate-limits/routerplex-rate-limits.yml)
- [Plans](plans/routerplex-plans.yml)
- [Packages](packages/routerplex-packages.yml)
- [Playground](https://routerplex.com/dashboard/playground)
- [Sandbox](sandbox/routerplex-sandbox.yml)
- [Benchmarks](https://routerplex.com/benchmarks.md)
- [Pricing](https://routerplex.com/pricing.md)

## Maintainers

**FN:** RouterPlex
**Email:** support@routerplex.com
**URL:** https://routerplex.com
