---
title: "RefundPolicy"
category: entities
tags: [config, rule]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: RefundPolicy

Defines named sets of cancellation rules for different services or periods.

## Database Table: `refund_policies`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `name` | VARCHAR(255) | NOT NULL | e.g., "Standard", "Holiday" |
| `service_type` | VARCHAR(50) | NOT NULL | TOUR, HOTEL, COACH |

## Relationships
- **Rules**: Contains multiple [[RefundPolicyRule]] entries.
- **Application**: Applied to [[Hotel]], [[Route]], and [[Tour]] templates.

## References
- [[database-schema]]
- [[chinh-sach-hoan-tien]]
