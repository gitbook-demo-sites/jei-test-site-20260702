---
description: "Every chart on the Telemetry dashboard, explained with healthy ranges and export options."
icon: chart-simple
layout:
  width: wide
---

# Dashboards & metrics

Telemetry dashboards are designed for weekly operating reviews. Use the charts together: velocity tells you what shipped, cycle time shows how long it took, and cumulative flow reveals where work is stuck.

## Velocity

Total fuel completed per launch window, with a 3-window rolling average. Scrubbed missions are excluded.

{% hint style="success" %}
A stable rolling average is more useful than a single heroic launch window. Look for repeatable throughput.
{% endhint %}

## Burndown

Remaining fuel in the current window, day by day, against an ideal line. Weekends are excluded if your work week is configured (see [Configuration](../../getting-started/configuration.md)).

## Cycle time

Time from **In Progress** to **Done**, shown as a scatter plot with p50/p85 bands.

| Percentile | Healthy range |
| ---------- | ------------- |
| p50 | 3 days or less |
| p85 | 7 days or less |

## Cumulative flow

Stacked area chart of mission counts per column over time. Widening bands indicate bottlenecks.

```mermaid
flowchart LR
    Backlog --> Ready
    Ready --> Progress["In Progress"]
    Progress --> Review
    Review --> Done
```

<details>
<summary>How to read a widening band</summary>

If the **In Review** band grows for several days while **Done** stays flat, reviewers are likely the bottleneck. Add review capacity, split large missions, or use an automation to escalate stale reviews.
</details>

## Exporting

Every chart exports as PNG or CSV. Dashboards can be shared with a read-only public link on Enterprise plans.

{% hint style="warning" %}
Changing workflow column mappings recalculates all historical metrics. Expect dashboards to shift after remapping.
{% endhint %}
