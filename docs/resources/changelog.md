# Changelog

## v3.2 — June 2026

* **New:** Mission dependencies — mark missions as blocked by others, visualized on the timeline
* **New:** CSV import for bulk mission creation
* **Improved:** Board rendering is ~40% faster on projects with 200+ missions
* **Fixed:** Launch window rollover occasionally duplicated sub-missions

## v3.1 — April 2026

* **New:** Figma embeds in mission descriptions
* **New:** `orbitly window close` CLI command
* **Improved:** Search now matches comment content, not just titles
* **Fixed:** Timezone drift in daily digest emails for UTC+ offsets

## v3.0 — February 2026

* **New:** Telemetry 2.0 — rebuilt dashboards with velocity trends, cycle time, and cumulative flow
* **New:** Service accounts for API automations
* **New:** Guest role for external collaborators
* **Breaking:** API v1 is deprecated; sunset scheduled for December 2026. Migrate to `/v2`.

## v2.9 — December 2025

* **New:** Zapier integration
* **Improved:** Webhook retry policy now caps at 5 attempts with backoff
* **Fixed:** `@mention` autocomplete failing for names with diacritics
