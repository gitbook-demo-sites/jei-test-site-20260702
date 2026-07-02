---
description: Official Orbitly SDKs for JavaScript and Python, plus community libraries.
icon: code
---

# SDKs

Official client libraries wrap the REST API with typed models, automatic pagination, retries, and rate-limit handling.

| SDK | Package | Min version |
| --- | ------- | ----------- |
| [JavaScript / TypeScript](javascript.md) | `@orbitly/sdk` | Node 18+ |
| [Python](python.md) | `orbitly` | Python 3.10+ |

{% hint style="info" %}
Both SDKs are generated from the same OpenAPI spec, so method names and models match across languages.
{% endhint %}

## Community libraries

Not maintained by Orbitly, but actively used:

* `orbitly-go` — Go client
* `orbitly-rs` — Rust client
* `orbitly-cli-extras` — extra CLI subcommands

## Versioning

SDKs follow semver and track API v2. Breaking API changes ship as a new SDK major version with a 6-month overlap window.
