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

## Standard Thresholds
The Travery SRS defines the following default refund rules based on `service_type`:
- **Tour**: 100% (≥7 days), 50% (3-6 days), 0% (<3 days).
- **Coach (Xe)**: 100% (≥2 hours), 0% (<2 hours).
- **Hotel**: 100% (≥72 hours), 50% (24-72 hours), 0% (<24 hours).
- Note: Travery-initiated cancellations result in a guaranteed 100% refund.

## Relationships
- **Rules**: Contains multiple [[RefundPolicyRule]] entries.
- **Application**: Applied to [[Hotel]], [[Route]], and [[Tour]] templates.

## References
- [[database-schema]]
- [[chinh-sach-hoan-tien]]
