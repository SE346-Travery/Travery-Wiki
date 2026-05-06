---
title: "Route"
category: entities
tags: [logistics, travel]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Route

Logical fixed-route connecting two [[Station]]s.

## Database Table: `routes`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `origin_station_id` | UUID | FK(stations.id) | Start point |
| `destination_station_id`| UUID | FK(stations.id) | End point |
| `distance_km` | DECIMAL(6,2) | NULL | Length of route |
| `estimated_hours` | DECIMAL(4,1) | NULL | Duration |
| `base_price` | DECIMAL(12,2) | NOT NULL | Base ticket cost |
| `refund_policy_id` | UUID | FK(refund_policies.id) | Cancellation rules |

## Relationships
- **Execution**: Spawns multiple [[CoachTrip]] instances.
- **Review**: Targets for user ratings.

## References
- [[database-schema]]
- [[xe-khach-tuyen-co-dinh]]
