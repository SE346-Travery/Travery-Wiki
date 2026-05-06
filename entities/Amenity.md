---
title: "Amenity"
category: entities
tags: [config, asset]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Amenity

Global catalog of facilities and services available at hotels or within rooms.

## Database Table: `amenities`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `name` | VARCHAR(100) | UNIQUE, NOT NULL | e.g., Pool, WiFi, AC |
| `icon_url` | VARCHAR(255) | NULL | SVG icon link |
| `type` | VARCHAR(50) | NOT NULL | HOTEL_AMENITY, ROOM_AMENITY |

## Relationships
- **Mapping**: Linked to [[Hotel]] via `hotel_amenities` and to [[RoomType]] via `room_type_amenities`.

## References
- [[database-schema]]
