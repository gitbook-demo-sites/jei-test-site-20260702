# Authentication

The Orbitly API uses bearer tokens over HTTPS. Base URL:

```
https://api.orbitly.example.com/v2
```

## API tokens

Create tokens under **Settings → API Tokens**. Two types:

| Type | Prefix | Use for |
| ---- | ------ | ------- |
| Live | `orb_live_` | Production integrations |
| Test | `orb_test_` | Development; operates on a sandbox workspace |

Tokens inherit the permissions of the user who created them. For automations, create a dedicated **service account**.

## Making requests

Pass the token in the `Authorization` header:

```bash
curl https://api.orbitly.example.com/v2/missions \
  -H "Authorization: Bearer orb_live_xxxxxxxxxxxx"
```

## Rate limits

| Plan | Requests/min |
| ---- | ------------ |
| Explorer | 60 |
| Team | 300 |
| Enterprise | 1,000 |

Rate limit state is returned on every response:

```
X-RateLimit-Limit: 300
X-RateLimit-Remaining: 297
X-RateLimit-Reset: 1782050400
```

Exceeding the limit returns `429 Too Many Requests` with a `Retry-After` header.

## Token security

* Never commit tokens to source control
* Rotate tokens under **Settings → API Tokens → Rotate**
* Tokens can be scoped to specific projects on Enterprise plans
