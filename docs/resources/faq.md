---
description: "Answers to common Orbitly setup, billing, mission, and troubleshooting questions."
icon: circle-question
---

# FAQ

## General

<details>
<summary>Is there a free plan?</summary>

Yes — the **Explorer** plan is free forever: 3 projects, 5 teammates, 30-day telemetry history.
</details>

<details>
<summary>Can I self-host Orbitly?</summary>

Self-hosting is available on the Enterprise plan as a Docker Compose or Helm deployment. Contact sales@orbitly.example.com.
</details>

<details>
<summary>How do I export my data?</summary>

**Settings → Workspace → Export** produces a ZIP with JSON and CSV exports of all projects, missions, and comments. API exports are also supported.
</details>

## Billing

<details>
<summary>How does seat counting work?</summary>

Admins and Members count as seats. Viewers and Guests are free on all plans.
</details>

<details>
<summary>Can I switch plans mid-cycle?</summary>

Yes. Upgrades are prorated immediately; downgrades take effect at the next renewal.
</details>

## Missions & boards

<details>
<summary>Can a mission have multiple assignees?</summary>

No — one owner per mission, by design. Use sub-missions to split work across people.
</details>

<details>
<summary>What happens to missions when a launch window closes?</summary>

Unfinished missions roll over to the backlog (or the next window, if configured). Their fuel estimate is flagged for re-review.
</details>

<details>
<summary>Is there a mission limit?</summary>

No limit on any paid plan. Explorer workspaces are capped at 500 active missions.
</details>

## Troubleshooting

<details>
<summary>My GitHub PRs are not linking to missions</summary>

Check that (1) the Orbitly GitHub App has access to the repository, and (2) the mission ID appears in the branch name or PR title exactly, e.g. `ORB-142`, case-sensitive.
</details>

<details>
<summary>I am not receiving Slack notifications</summary>

Re-authorize the Slack integration under **Settings → Integrations**. If notifications stopped after a Slack workspace rename, disconnect and reconnect.
</details>
