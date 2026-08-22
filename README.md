# RouterPlex (routerplex)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
