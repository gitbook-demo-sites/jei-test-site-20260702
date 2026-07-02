# Projects & Missions

Everything in Orbitly lives inside a project.

## Projects

A project is a container for related work — a product area, a client engagement, or a team. Projects have:

* A **board** (Kanban or list view)
* A **timeline** (Gantt-style view of launch windows)
* **Telemetry** (charts and reports)

### Archiving

Archived projects become read-only but stay searchable. Restore anytime from **Settings → Archived Projects**.

## Missions

Missions are individual units of work. Each mission has:

| Field | Description |
| ----- | ----------- |
| Title | Short summary of the work |
| Status | Column on the board (e.g. Backlog, In Progress, Done) |
| Assignee | One owner per mission |
| Priority | Critical / High / Medium / Low |
| Fuel | Effort estimate in points (1, 2, 3, 5, 8) |
| Labels | Freeform tags for filtering |

### Sub-missions

Break large missions into sub-missions. A parent mission shows aggregate progress:

```
[ORB-142] Redesign checkout flow          ███████░░░ 70%
  ├─ [ORB-143] New payment form           ✓ Done
  ├─ [ORB-144] Address autocomplete       ✓ Done
  └─ [ORB-145] Error state review         ◌ In Progress
```

### Mission states

Missions move through your project's workflow columns. Two states are special:

* **Done** — counts toward velocity, triggers automations
* **Scrubbed** — cancelled; excluded from all metrics

> **Tip:** Use `Cmd+K` anywhere in the app to jump to any mission by ID or title.
