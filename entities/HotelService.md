---
title: "HotelService"
category: entities
tags: [asset, add-on]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: HotelService

Specific add-on services provided by a [[Hotel]] (e.g., Breakfast, Laundry).

## Database Table: `hotel_services`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `hotel_id` | UUID | FK(hotels.id) | Provider hotel |
| `category` | VARCHAR(50) | NOT NULL | FOOD, SPA, LAUNDRY, OTHER |
| `name` | VARCHAR(100) | NOT NULL | Service title |
| `price` | DECIMAL(12,2)| NOT NULL | Cost per unit |
| `unit` | VARCHAR(50) | NOT NULL | Kg, Package, Person, etc. |
| `description` | TEXT | NULL | Service details |
| `is_active` | BOOLEAN | DEFAULT TRUE | Availability status |

## Relationships
- **Booking**: Requested via [[AddOnOrder]].

## References
- [[database-schema]]
- [[add-on]]
