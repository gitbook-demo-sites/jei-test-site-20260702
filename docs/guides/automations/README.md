---
description: Automate repetitive workflows in Orbitly with rules, triggers, and actions.
icon: bolt
---

# Automations

Automations let you eliminate repetitive board management. Each automation is a **rule** made of a trigger, optional conditions, and one or more actions.

{% hint style="info" %}
Automations are available on the Team plan and above. Explorer workspaces can create 1 automation per project as a trial.
{% endhint %}

## How rules work

```
TRIGGER          CONDITION              ACTION
Mission moved →  column is "Done"   →   Post to #launches
                 AND label ≠ "internal"  Notify assignee's manager
```

Rules run in the order listed on the **Automations** page. A single event can match multiple rules.

## In this section

* [Rules & triggers](rules.md) — every available trigger, condition, and action
* [Example recipes](examples.md) — copy-paste automations for common workflows

{% hint style="warning" %}
Automations can trigger other automations, but chains are capped at 5 hops to prevent loops.
{% endhint %}
