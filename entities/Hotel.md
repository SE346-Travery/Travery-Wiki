---
title: "Hotel"
category: entities
tags: [asset, accommodation]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: Hotel

Represents a lodging establishment owned and operated by Travery.

## Database Table: `hotels`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `name` | VARCHAR(255) | NOT NULL | Hotel name |
| `star_rating` | INT | NOT NULL | 1-5 stars |
| `description` | TEXT | NULL | Detailed intro |
| `address` | VARCHAR(500) | NOT NULL | Physical address |
| `city_province` | VARCHAR(100) | NOT NULL | Location |
| `latitude/longitude` | DECIMAL | NOT NULL | GPS coordinates |
| `check_in_time` | TIME | DEFAULT '14:00' | Standard arrival |
| `check_out_time` | TIME | DEFAULT '12:00' | Standard departure |
| `refund_policy_id` | UUID | FK(refund_policies.id) | Cancellation rules |

## Relationships
- **Inventory**: Contains multiple [[RoomType]]s and physical [[Room]]s.
- **Staff**: Employs [[Receptionist]]s.
- **Services**: Offers multiple [[HotelService]]s (Add-ons).
- **Amenities**: Linked via `hotel_amenities` to general [[Amenity]] items.
- **Tour**: Acts as an accommodation point for [[Tour]] templates.

## References
- [[database-schema]]
- [[khach-san]]
