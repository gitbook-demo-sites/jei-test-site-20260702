# Configuration

Configure Orbitly at the workspace, project, and user level.

## Workspace settings

Admins can configure these under **Settings → Workspace**:

* **Default timezone** — used for launch window boundaries and reports
* **Work week** — which days count toward velocity calculations
* **Mission ID prefix** — e.g. `ORB-123` vs `WEB-123`
* **SSO** — SAML 2.0 on the Enterprise plan

## Project settings

Each project has its own settings page:

* **Workflow columns** — customize the Kanban board stages
* **Mission templates** — pre-filled fields for common work types
* **Automations** — e.g. "when a mission moves to Done, notify #launches"

## CLI configuration

The CLI reads from `~/.config/orbitly/config.toml`:

```toml
[core]
default_workspace = "acme-inc"
editor = "vim"

[output]
format = "table"   # table | json | csv
color = true

[aliases]
st = "mission list --mine --status open"
```

Environment variables override the config file:

| Variable | Purpose |
| -------- | ------- |
| `ORBITLY_TOKEN` | API token for authentication |
| `ORBITLY_WORKSPACE` | Default workspace slug |
| `ORBITLY_API_URL` | Override API base URL (self-hosted) |

## User preferences

Each user controls their own notification settings under **Settings → Notifications**: email digests, Slack DMs, and in-app alerts can be toggled independently.
