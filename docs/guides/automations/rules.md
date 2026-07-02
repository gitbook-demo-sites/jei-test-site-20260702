---
description: "Full reference for automation triggers, conditions, actions, and execution history."
icon: list-check
---

# Rules & triggers

Rules are evaluated whenever their trigger event occurs. If every condition passes, Orbitly runs the configured actions in order.

## Triggers

| Trigger | Fires when |
| ------- | ---------- |
| Mission created | Any new mission in the project |
| Mission moved | A mission changes column |
| Assignee changed | Ownership transfers |
| Fuel changed | The estimate is updated |
| Window opened / closed | A launch window starts or ends |
| Review decision | A reviewer approves or requests changes |

{% hint style="info" %}
Use the most specific trigger available. Broad triggers are powerful, but they are easier to over-fire.
{% endhint %}

## Conditions

Conditions filter which events actually run the actions. Combine with AND/OR:

* Column **is / is not** a specific column
* Label **contains / doesn't contain**
* Priority **is at least** (Critical > High > Medium > Low)
* Assignee **is / is in team**
* Fuel **greater / less than**

## Actions

Actions run from top to bottom. If one action fails, the remaining actions are skipped and the run is marked failed in history.

{% tabs %}
{% tab title="Board updates" %}
* Move mission to a column
* Set priority, label, or fuel
* Assign to a person or round-robin within a team
* Create a follow-up mission from a template
{% endtab %}

{% tab title="Notifications" %}
* Post to a Slack channel
* Send a direct notification
* Add a mission comment
* Request review from a team
{% endtab %}

{% tab title="Integrations" %}
* Send a webhook
* Add a GitHub status comment
* Export a payload to a reporting destination
{% endtab %}
{% endtabs %}

## Variables

Action payloads support variables:

| Variable | Example value |
| -------- | ------------- |
| `{{mission.id}}` | `ORB-142` |
| `{{mission.title}}` | `Redesign checkout flow` |
| `{{mission.assignee}}` | `sam@example.com` |
| `{{window.name}}` | `July Launch Window` |

{% hint style="info" %}
Variables are resolved at execution time. If a field is empty, Orbitly leaves the variable blank rather than failing the rule.
{% endhint %}

## Execution log

Every rule keeps a 30-day execution log under **Automations → History**, including skipped runs (condition not met) and failures with error details.

<details>
<summary>Recommended naming pattern</summary>

Use names that describe the trigger and outcome:

* `When bug is created, assign QA`
* `When review is stale, notify manager`
* `When large mission ships, post to wins`

Avoid generic names like `Slack automation` or `Rule 1`.
</details>
