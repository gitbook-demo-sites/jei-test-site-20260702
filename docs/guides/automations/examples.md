---
description: "Copy-paste automation recipes for bug triage, launches, reviews, sprint hygiene, and warehouse events."
icon: wand-magic-sparkles
---

# Example recipes

Use these recipes as starting points. Adjust labels, teams, channels, and templates to match your workspace.

{% hint style="info" %}
Before enabling a recipe for the whole project, run it in draft mode and inspect the execution history for skipped and matched events.
{% endhint %}

## Bug triage

{% tabs %}
{% tab title="Rule" %}
* **When:** mission created
* **If:** label contains `bug`
* **Then:** set priority High, assign round-robin to team `QA`, and post to `#bug-triage`
{% endtab %}

{% tab title="Slack message" %}
```text
New bug needs triage: {{mission.id}} - {{mission.title}}
Assigned to: {{mission.assignee}}
```
{% endtab %}
{% endtabs %}

## Celebrate launches

* **When:** mission moved
* **If:** column is `Done` and fuel is greater than or equal to `5`
* **Then:** post to `#wins`

```text
{{mission.assignee}} shipped {{mission.title}} in {{window.name}}.
```

## Escalate stale reviews

{% stepper %}
{% step %}
## Detect the stale review

**When** review requested and no decision is made after 48 hours.
{% endstep %}

{% step %}
## Notify the owner

Notify the reviewer's manager and mention the mission owner.
{% endstep %}

{% step %}
## Mark the mission

Add the `review-stale` label so it appears in the team's blocked-work view.
{% endstep %}
{% endstepper %}

## Sprint hygiene

{% tabs %}
{% tab title="Rollover cleanup" %}
**When** window closed **then** move unfinished missions to `Backlog`, add label `rolled-over`, create follow-up mission "Re-estimate rolled missions" assigned to the project lead.
{% endtab %}

{% tab title="Kickoff checklist" %}
**When** window opened **then** create missions from the `sprint-kickoff` template: confirm capacity, review carry-over, update stakeholder doc.
{% endtab %}
{% endtabs %}

## Custom webhook to a data warehouse

**When** mission moved **if** column is `Done` **then** send webhook:

```json
{
  "event": "shipped",
  "id": "{{mission.id}}",
  "title": "{{mission.title}}",
  "fuel": "{{mission.fuel}}",
  "window": "{{window.name}}"
}
```

{% hint style="success" %}
This recipe works best when the receiving endpoint accepts quickly and processes the event asynchronously.
{% endhint %}
