# Webhooks

Webhooks let you receive real-time HTTP callbacks when things happen in Orbitly.

## Creating a webhook

Under **Settings → Webhooks**, click **New Webhook** and provide:

* **URL** — must be HTTPS
* **Events** — one or more event types to subscribe to
* **Secret** — used to sign payloads (auto-generated if blank)

## Event types

| Event | Fired when |
| ----- | ---------- |
| `mission.created` | A new mission is created |
| `mission.updated` | Any mission field changes |
| `mission.status_changed` | A mission moves between columns |
| `window.opened` | A launch window starts |
| `window.closed` | A launch window ends |
| `comment.created` | A comment is posted |

## Payload format

```json
{
  "event": "mission.status_changed",
  "timestamp": "2026-07-02T14:30:00Z",
  "workspace": "acme-inc",
  "data": {
    "mission_id": "ORB-142",
    "title": "Redesign checkout flow",
    "from_status": "in_progress",
    "to_status": "done",
    "actor": "usr_8f3ka92"
  }
}
```

## Verifying signatures

Every request includes an `X-Orbitly-Signature` header — an HMAC-SHA256 of the raw body using your webhook secret:

```python
import hmac, hashlib

def verify(body: bytes, signature: str, secret: str) -> bool:
    expected = hmac.new(secret.encode(), body, hashlib.sha256).hexdigest()
    return hmac.compare_digest(expected, signature)
```

## Retries

Failed deliveries (non-2xx response) are retried with exponential backoff: 1 min, 5 min, 30 min, 2 h, 12 h. After 5 failures the webhook is paused and admins are notified.
