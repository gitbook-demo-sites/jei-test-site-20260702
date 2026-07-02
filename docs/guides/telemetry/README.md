---
description: Understand your team's velocity, cycle time, and delivery trends.
icon: chart-line
---

# Telemetry

Telemetry is Orbitly's reporting suite. Every project gets a dashboard; workspace-level rollups are available on Team and Enterprise plans.

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
