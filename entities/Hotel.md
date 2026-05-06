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
| `check_in_time` | TIME | DEFAULT '12:00' | Standard arrival |
| `check_out_time` | TIME | DEFAULT '12:00' | Standard departure |
| `refund_policy_id` | UUID | FK(refund_policies.id) | Cancellation rules |

## Constraints & Business Rules
- **Check-in/Check-out**: Check-in is available strictly from **12:00 noon**. Check-out is before **12:00 noon**.
- **Late Check-out**: A penalty fee of 20,000 VND per hour is applied and added to the final bill.
- **Identity**: Check-in requires presentation of a physical ID matching the booking details.

## Relationships
- **Inventory**: Contains multiple [[RoomType]]s and physical [[Room]]s.
- **Staff**: Employs [[Receptionist]]s.
- **Services**: Offers multiple [[HotelService]]s (Add-ons).
- **Amenities**: Linked via `hotel_amenities` to general [[Amenity]] items.
- **Tour**: Acts as an accommodation point for [[Tour]] templates.

## References
- [[database-schema]]
- [[khach-san]]
