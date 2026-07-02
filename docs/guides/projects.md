---
description: "Understand Orbitly's core building blocks: projects, missions, launch windows, and telemetry."
icon: diagram-project
---

# Projects & Missions

Everything in Orbitly lives inside a project.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody>
<tr>
  <td><h3><i class="fa-folder" style="color:$primary;">:file_folder:</i></h3></td>
  <td><strong>Projects</strong></td>
  <td>Group related work by team, product area, or customer initiative.</td>
  <td><a href="#projects">projects</a></td>
</tr>
<tr>
  <td><h3><i class="fa-list-check" style="color:$primary;">:white_check_mark:</i></h3></td>
  <td><strong>Missions</strong></td>
  <td>Track individual units of work with status, owner, priority, and fuel.</td>
  <td><a href="#missions">missions</a></td>
</tr>
<tr>
  <td><h3><i class="fa-chart-line" style="color:$primary;">:chart_with_upwards_trend:</i></h3></td>
  <td><strong>Telemetry</strong></td>
  <td>Measure flow, delivery confidence, and launch-window health.</td>
  <td><a href="telemetry/README.md">telemetry</a></td>
</tr>
</tbody></table>

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

| Mission | Status |
| --- | --- |
| `ORB-142` Redesign checkout flow | 70% complete |
| `ORB-143` New payment form | Done |
| `ORB-144` Address autocomplete | Done |
| `ORB-145` Error state review | In progress |

### Mission states

Missions move through your project's workflow columns. Two states are special:

* **Done** — counts toward velocity, triggers automations
* **Scrubbed** — cancelled; excluded from all metrics

> **Tip:** Use `Cmd+K` anywhere in the app to jump to any mission by ID or title.
