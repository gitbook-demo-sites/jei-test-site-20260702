---
description: "A lightweight review process for keeping test content clean."
icon: code-merge
---

# Review process

Use change requests when edits should be reviewed before publishing.

```mermaid
sequenceDiagram
    participant Author
    participant Reviewer
    participant Site
    Author->>Reviewer: Opens change request
    Reviewer->>Author: Leaves comments or approves
    Author->>Reviewer: Resolves comments
    Reviewer->>Site: Merges approved changes
```

## Review checklist

| Check | Pass criteria |
| --- | --- |
| Purpose | The page has one clear reader goal. |
| Navigation | The page is linked from the right section. |
| Accuracy | Claims are specific and current. |
| Links | Internal and external links open correctly. |
| Search | The page uses terms a reader would search for. |

## Reviewer notes

Reviewers should focus on clarity, correctness, and findability. Save style preferences for patterns that will repeat across the site.
