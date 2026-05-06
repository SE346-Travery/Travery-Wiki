---
title: "RoomType"
category: entities
tags: [asset, hotel]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: RoomType

Categories of lodging offered by a [[Hotel]] (e.g., Standard, VIP, Suite).

## Database Table: `room_types`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `hotel_id` | UUID | FK(hotels.id) | Parent hotel |
| `name` | VARCHAR(255) | NOT NULL | Type name |
| `description` | TEXT | NULL | Amenities/Layout info |
| `base_price` | DECIMAL(12,2)| NOT NULL | Standard rate |
| `capacity_adults`| INT | NOT NULL | Max adults |
| `capacity_children`| INT | DEFAULT 0 | Max children |
| `bed_type` | VARCHAR(50) | NOT NULL | DOUBLE, SINGLE, TWIN |

## Relationships
- **Parent**: Belong to one [[Hotel]].
- **Inventory**: Contains multiple physical [[Room]]s.
- **Booking**: Target for [[HotelBookingDetail]].
- **Amenities**: Linked via `room_type_amenities` to [[Amenity]].

## References
- [[database-schema]]
- [[khach-san]]
