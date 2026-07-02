---
description: "Authenticate to the Orbitly API with bearer tokens, service accounts, scopes, and rate limits."
icon: key
---

# Authentication

The Orbitly API uses bearer tokens over HTTPS.

```text
https://api.orbitly.example.com/v2
```

{% hint style="info" %}
Use test tokens while building integrations. Switch to live tokens only after the workflow is validated in a sandbox workspace.
{% endhint %}

## API tokens

Create tokens under **Settings > API Tokens**.

| Type | Prefix | Use for |
| ---- | ------ | ------- |
| Live | `orb_live_` | Production integrations |
| Test | `orb_test_` | Development and sandbox workspaces |

Tokens inherit the permissions of the user who created them. For automations, create a dedicated **service account** so ownership is not tied to a human user.

## Make a request

{% tabs %}
{% tab title="cURL" %}
```bash
curl https://api.orbitly.example.com/v2/missions \
  -H "Authorization: Bearer orb_live_xxxxxxxxxxxx"
```
{% endtab %}

{% tab title="JavaScript" %}
```typescript
const res = await fetch("https://api.orbitly.example.com/v2/missions", {
  headers: {
    Authorization: `Bearer ${process.env.ORBITLY_TOKEN}`,
  },
});
```
{% endtab %}

{% tab title="Python" %}
```python
import os
import requests

res = requests.get(
    "https://api.orbitly.example.com/v2/missions",
    headers={"Authorization": f"Bearer {os.environ['ORBITLY_TOKEN']}"},
)
```
{% endtab %}
{% endtabs %}

## Rate limits

| Plan | Requests/min |
| ---- | ------------ |
| Explorer | 60 |
| Team | 300 |
| Enterprise | 1,000 |

Rate limit state is returned on every response:

```text
X-RateLimit-Limit: 300
X-RateLimit-Remaining: 297
X-RateLimit-Reset: 1782050400
```

Exceeding the limit returns `429 Too Many Requests` with a `Retry-After` header.

## Token security

{% stepper %}
{% step %}
## Store tokens in a secret manager

Do not commit tokens to source control or paste them into issue comments.
{% endstep %}

{% step %}
## Scope tokens narrowly

Enterprise workspaces can scope tokens to specific projects.
{% endstep %}

{% step %}
## Rotate regularly

Rotate tokens under **Settings > API Tokens > Rotate**, especially after team or vendor changes.
{% endstep %}
{% endstepper %}
