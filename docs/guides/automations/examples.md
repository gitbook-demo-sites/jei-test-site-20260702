---
description: Copy-paste automation recipes for common team workflows.
---

# Example recipes

## Auto-triage new bugs

> **When** mission created **if** label contains `bug` **then** set priority High, assign round-robin to team `QA`, post to `#bug-triage`.

## Celebrate launches

> **When** mission moved **if** column is `Done` **and** fuel ≥ 5 **then** post to `#wins`: 🎉 `{{mission.assignee}}` shipped `{{mission.title}}`.

## Escalate stale reviews

> **When** review requested **if** no decision after 48 h **then** notify reviewer's manager and add label `review-stale`.

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
