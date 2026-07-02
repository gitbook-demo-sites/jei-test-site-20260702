---
description: Full reference for automation triggers, conditions, and actions.
---

# Rules & triggers

## Triggers

| Trigger | Fires when |
| ------- | ---------- |
| Mission created | Any new mission in the project |
| Mission moved | A mission changes column |
| Assignee changed | Ownership transfers |
| Fuel changed | The estimate is updated |
| Window opened / closed | A launch window starts or ends |
| Review decision | A reviewer approves or requests changes |

## Conditions

Conditions filter which events actually run the actions. Combine with AND/OR:

* Column **is / is not** a specific column
* Label **contains / doesn't contain**
* Priority **is at least** (Critical > High > Medium > Low)
* Assignee **is / is in team**
* Fuel **greater / less than**

## Actions

* Move mission to a column
* Set priority, label, or fuel
* Assign to a person or round-robin within a team
* Post to a Slack channel
* Send a webhook (custom JSON payload with mission variables)
* Create a follow-up mission from a template

{% hint style="info" %}
Action payloads support variables: `{{mission.id}}`, `{{mission.title}}`, `{{mission.assignee}}`, `{{window.name}}`.
{% endhint %}

## Execution log

Every rule keeps a 30-day execution log under **Automations → History**, including skipped runs (condition not met) and failures with error details.
