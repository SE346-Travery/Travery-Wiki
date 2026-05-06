---
title: "RefundPolicyRule"
category: entities
tags: [config, detail]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: RefundPolicyRule

Specific time-based threshold for refund calculations.

## Database Table: `refund_policy_rules`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `refund_policy_id`| UUID | FK(refund_policies.id) | Parent policy |
| `hours_before_departure`| INT | NOT NULL | Threshold (e.g., 168h = 7d) |
| `refund_percentage`| DECIMAL(5,2)| NOT NULL | % to return (0-100) |

## References
- [[database-schema]]
- [[chinh-sach-hoan-tien]]
