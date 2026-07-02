---
description: Understand your team's velocity, cycle time, and delivery trends.
icon: chart-line
---

# Telemetry

Telemetry is Orbitly's reporting suite. Every project gets a dashboard; workspace-level rollups are available on Team and Enterprise plans.

Telemetry answers three operating questions:

<table data-view="cards">
  <thead>
    <tr>
      <th width="48"></th>
      <th></th>
      <th></th>
      <th data-hidden data-card-target data-type="content-ref"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><i class="fa-gauge-high"></i></td>
      <td><strong>How much did we ship?</strong></td>
      <td>Velocity and completed fuel by launch window.</td>
      <td><a href="dashboards.md#velocity">velocity</a></td>
    </tr>
    <tr>
      <td><i class="fa-stopwatch"></i></td>
      <td><strong>How long does work take?</strong></td>
      <td>Cycle time from start to completion.</td>
      <td><a href="dashboards.md#cycle-time">cycle time</a></td>
    </tr>
    <tr>
      <td><i class="fa-chart-area"></i></td>
      <td><strong>Where are bottlenecks?</strong></td>
      <td>Cumulative flow and aging work by column.</td>
      <td><a href="dashboards.md#cumulative-flow">flow</a></td>
    </tr>
  </tbody>
</table>

## Setting up

{% stepper %}
{% step %}
**Enable telemetry for the project**

Under **Project Settings → Telemetry**, toggle it on. Historical data backfills from the project's creation date.
{% endstep %}

{% step %}
**Map your workflow columns**

Tell Orbitly which columns mean "work started" and "work finished" so cycle time is measured correctly.
{% endstep %}

{% step %}
**Set a fuel baseline**

After 3 launch windows, Orbitly calibrates expected velocity automatically.
{% endstep %}
{% endstepper %}

## In this section

* [Dashboards & metrics](dashboards.md)

{% hint style="info" %}
Telemetry data is available via the API at `GET /telemetry?project={id}` for custom reporting.
{% endhint %}

## Data freshness

Dashboard metrics update when mission state changes. Workspace rollups refresh every 15 minutes.

| Data source | Refresh behavior |
| ----------- | ---------------- |
| Mission status | Near real time |
| Launch windows | Near real time |
| Workspace rollups | Every 15 minutes |
| CSV exports | Generated on demand |
