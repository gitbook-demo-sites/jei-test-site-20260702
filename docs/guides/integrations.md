---
description: "Connect Orbitly with Slack, GitHub, Figma, Zapier, APIs, and webhooks."
icon: puzzle-piece
---

# Integrations

Connect Orbitly to the tools your team already uses. All integrations are managed under **Settings > Integrations**.

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
      <td><i class="fa-slack"></i></td>
      <td><strong>Slack</strong></td>
      <td>Create missions, route updates, and keep launch channels informed.</td>
      <td><a href="#slack">slack</a></td>
    </tr>
    <tr>
      <td><i class="fa-github"></i></td>
      <td><strong>GitHub</strong></td>
      <td>Connect missions to branches, pull requests, and releases.</td>
      <td><a href="#github">github</a></td>
    </tr>
    <tr>
      <td><i class="fa-plug"></i></td>
      <td><strong>Webhooks</strong></td>
      <td>Send real-time events into internal systems and data pipelines.</td>
      <td><a href="webhooks.md">webhooks</a></td>
    </tr>
  </tbody>
</table>

## Slack

Use Slack to keep project conversations close to the work.

* Get mission notifications in any channel
* Create missions from Slack with `/orbitly new`
* Unfurl mission links with live status
* Route review requests to project channels

{% stepper %}
{% step %}
## Connect Slack

Click **Connect Slack** and authorize your workspace.
{% endstep %}

{% step %}
## Map projects to channels

Choose a default channel per project, such as `#product-launches` or `#bug-triage`.
{% endstep %}

{% step %}
## Choose notification events

Enable only the events the channel should act on, such as blocked missions, completed launches, or review requests.
{% endstep %}
{% endstepper %}

## GitHub

Link code activity to mission progress by including the mission ID, such as `ORB-142`, in a branch name, commit message, or pull request title.

| GitHub event | Orbitly behavior |
| ------------ | ---------------- |
| Branch created | Links the branch to the mission |
| Pull request opened | Moves mission to **In Review** |
| Pull request merged | Moves mission to **Done** if no required review is pending |
| Pull request closed | Adds a comment with the close reason |

{% hint style="info" %}
Install the Orbitly GitHub App on only the repositories that should sync work state. You can add repositories later without reconnecting the integration.
{% endhint %}

## Figma

Paste any Figma link into a mission description to embed a live preview thumbnail. Orbitly keeps the link attached to the mission, so reviewers can jump directly from implementation work to design context.

## Zapier

For no-code workflows, the Orbitly Zapier app exposes common triggers and actions.

| Triggers | Actions |
| -------- | ------- |
| Mission created | Create mission |
| Mission status changed | Update mission |
| Launch window closed | Add comment |
| Review requested | Send message |

## API and webhooks

Use the REST API and webhooks for custom integrations.

* Start with [Authentication](../api-reference/authentication.md) for token setup.
* Use [Webhooks](webhooks.md) for event delivery.
* Use [SDKs](../api-reference/sdks/README.md) for typed client libraries.
