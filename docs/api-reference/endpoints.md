# Endpoints

All endpoints are relative to `https://api.orbitly.example.com/v2`. Responses are JSON. List endpoints support `?limit=` (max 100) and cursor-based pagination via `?after=`.

## Missions

### List missions

```
GET /missions?project=prj_a8x2k&status=open
```

```json
{
  "data": [
    {
      "id": "ORB-142",
      "title": "Redesign checkout flow",
      "status": "in_progress",
      "assignee": "usr_8f3ka92",
      "priority": "high",
      "fuel": 5,
      "created_at": "2026-06-12T09:14:00Z"
    }
  ],
  "next_cursor": "eyJpZCI6MTQyfQ"
}
```

### Create a mission

```
POST /missions
```

```json
{
  "project": "prj_a8x2k",
  "title": "Add dark mode toggle",
  "priority": "medium",
  "fuel": 3
}
```

### Update a mission

```
PATCH /missions/ORB-142
```

Any field from the mission object can be updated. Status changes fire webhooks.

## Projects

| Method | Path | Description |
| ------ | ---- | ----------- |
| `GET` | `/projects` | List projects |
| `POST` | `/projects` | Create a project |
| `GET` | `/projects/{id}` | Get project details |
| `DELETE` | `/projects/{id}` | Archive a project |

## Launch windows

| Method | Path | Description |
| ------ | ---- | ----------- |
| `GET` | `/windows?project={id}` | List launch windows |
| `POST` | `/windows` | Create a launch window |
| `POST` | `/windows/{id}/close` | Close a window early |

## Users

| Method | Path | Description |
| ------ | ---- | ----------- |
| `GET` | `/users/me` | Current authenticated user |
| `GET` | `/users?workspace={slug}` | List workspace members |
