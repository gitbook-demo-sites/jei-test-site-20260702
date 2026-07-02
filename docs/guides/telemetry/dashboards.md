---
description: Every chart on the Telemetry dashboard, explained.
---

# Dashboards & metrics

## Velocity

Total fuel completed per launch window, with a 3-window rolling average. Scrubbed missions are excluded.

## Burndown

Remaining fuel in the current window, day by day, against an ideal line. Weekends are excluded if your work week is configured (see [Configuration](../../getting-started/configuration.md)).

## Cycle time

Time from **In Progress** to **Done**, shown as a scatter plot with p50/p85 bands.

| Percentile | Healthy range |
| ---------- | ------------- |
| p50 | ≤ 3 days |
| p85 | ≤ 7 days |

## Cumulative flow

Stacked area chart of mission counts per column over time. Widening bands indicate bottlenecks.

## Exporting

Every chart exports as PNG or CSV. Dashboards can be shared with a read-only public link on Enterprise plans.

{% hint style="warning" %}
Changing workflow column mappings recalculates all historical metrics — expect dashboards to shift after remapping.
{% endhint %}
