---
description: "Product updates, API changes, fixes, and deprecations."
icon: clock-rotate-left
layout:
  width: wide
---

# Changelog

{% updates format="full" %}
{% update date="2026-06-15" tags="product,fix" %}
## v3.2

* Mission dependencies can now mark missions as blocked by other work and visualize blockers on the timeline.
* CSV import is available for bulk mission creation.
* Board rendering is about 40% faster on projects with 200+ missions.
* Launch window rollover no longer duplicates sub-missions in edge cases.
{% endupdate %}

{% update date="2026-04-10" tags="product,api" %}
## v3.1

* Figma embeds are supported in mission descriptions.
* The CLI now includes `orbitly window close`.
* Search matches comment content, not just mission titles.
* Daily digest timezone handling is more reliable for UTC+ offsets.
{% endupdate %}

{% update date="2026-02-18" tags="product,api,breaking" %}
## v3.0

* Telemetry 2.0 adds velocity trends, cycle time, and cumulative flow dashboards.
* Service accounts are available for API automations.
* Guest roles support external collaborators.
* API v1 is deprecated and scheduled for sunset in December 2026. Migrate to `/v2`.
{% endupdate %}

{% update date="2025-12-08" tags="product,fix" %}
## v2.9

* Zapier integration is now available.
* Webhook retry policy now caps at five attempts with backoff.
* `@mention` autocomplete works for names with diacritics.
{% endupdate %}
{% endupdates %}
