---
description: Official Orbitly SDKs for JavaScript and Python, plus community libraries.
icon: code
---

# SDKs

Official client libraries wrap the REST API with typed models, automatic pagination, retries, and rate-limit handling.

<table data-view="cards">
  <thead>
    <tr>
      <th width="48"></th>
      <th></th>
      <th></th>
      <th data-hidden data-card-target data-type="content-ref"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><i class="fa-js"></i></td>
      <td><strong>JavaScript / TypeScript</strong></td>
      <td>Typed client for Node.js services, build scripts, and internal tools.</td>
      <td><a href="javascript.md">javascript</a></td>
    </tr>
    <tr>
      <td><i class="fa-python"></i></td>
      <td><strong>Python</strong></td>
      <td>Python client for data pipelines, notebooks, and backend automation.</td>
      <td><a href="python.md">python</a></td>
    </tr>
  </tbody>
</table>

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

{% hint style="success" %}
Use SDKs for production integrations. Use raw HTTP examples when debugging requests or building a client for an unsupported language.
{% endhint %}
