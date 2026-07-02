# Errors

The API uses conventional HTTP status codes and returns a structured error body:

```json
{
  "error": {
    "code": "mission_not_found",
    "message": "No mission with ID ORB-999 exists in this workspace.",
    "doc_url": "https://docs.orbitly.example.com/api-reference/errors"
  }
}
```

## Status codes

| Code | Meaning |
| ---- | ------- |
| `400` | Malformed request body or invalid parameters |
| `401` | Missing or invalid API token |
| `403` | Token valid but lacks permission for this resource |
| `404` | Resource doesn't exist or isn't visible to you |
| `409` | Conflict — e.g. duplicate mission ID prefix |
| `422` | Validation failed; see `error.fields` for details |
| `429` | Rate limit exceeded; respect `Retry-After` |
| `500` | Something broke on our end — retry with backoff |

## Validation errors

`422` responses include a per-field breakdown:

```json
{
  "error": {
    "code": "validation_failed",
    "message": "One or more fields are invalid.",
    "fields": {
      "fuel": "must be one of: 1, 2, 3, 5, 8",
      "priority": "unknown value 'urgent'"
    }
  }
}
```

## Common error codes

| Code | Fix |
| ---- | --- |
| `token_expired` | Rotate the token in Settings |
| `workspace_suspended` | Billing issue — contact an admin |
| `mission_locked` | Mission is in a closed launch window |
| `plan_limit_reached` | Upgrade plan or archive unused projects |
