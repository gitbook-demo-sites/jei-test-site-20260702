# Integrations

Connect Orbitly to the tools your team already uses. All integrations are managed under **Settings → Integrations**.

## Slack

* Get mission notifications in any channel
* Create missions from Slack with `/orbitly new`
* Unfurl mission links with live status

**Setup:** click **Connect Slack**, authorize the workspace, then map projects to channels.

## GitHub

* Link commits and PRs to missions by including the mission ID (e.g. `ORB-142`) in the branch name or commit message
* Missions auto-move to **In Review** when a linked PR opens, and **Done** when it merges

**Setup:** install the Orbitly GitHub App on your organization and choose repositories.

## Figma

Paste any Figma link into a mission description to embed a live preview thumbnail.

## Zapier

For everything else, the Orbitly Zapier app exposes:

| Triggers | Actions |
| -------- | ------- |
| Mission created | Create mission |
| Mission status changed | Update mission |
| Launch window closed | Add comment |

## API & webhooks

For custom integrations, see the [API Reference](../api-reference/authentication.md) and [Webhooks guide](webhooks.md).
