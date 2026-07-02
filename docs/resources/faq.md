# FAQ

## General

### Is there a free plan?

Yes — the **Explorer** plan is free forever: 3 projects, 5 teammates, 30-day telemetry history.

### Can I self-host Orbitly?

Self-hosting is available on the Enterprise plan as a Docker Compose or Helm deployment. Contact sales@orbitly.example.com.

### How do I export my data?

**Settings → Workspace → Export** produces a ZIP with JSON and CSV exports of all projects, missions, and comments. API exports are also supported.

## Billing

### How does seat counting work?

Admins and Members count as seats. Viewers and Guests are free on all plans.

### Can I switch plans mid-cycle?

Yes. Upgrades are prorated immediately; downgrades take effect at the next renewal.

## Missions & boards

### Can a mission have multiple assignees?

No — one owner per mission, by design. Use sub-missions to split work across people.

### What happens to missions when a launch window closes?

Unfinished missions roll over to the backlog (or the next window, if configured). Their fuel estimate is flagged for re-review.

### Is there a mission limit?

No limit on any paid plan. Explorer workspaces are capped at 500 active missions.

## Troubleshooting

### My GitHub PRs aren't linking to missions

Check that (1) the Orbitly GitHub App has access to the repository, and (2) the mission ID appears in the branch name or PR title exactly, e.g. `ORB-142`, case-sensitive.

### I'm not receiving Slack notifications

Re-authorize the Slack integration under **Settings → Integrations**. If notifications stopped after a Slack workspace rename, disconnect and reconnect.
