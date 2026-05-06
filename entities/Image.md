---
title: "Image"
category: entities
tags: [auxiliary, asset]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: Image

Polymorphic gallery management for various assets.

## Database Table: `images`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `entity_id` | UUID | NOT NULL | ID of the target object |
| `entity_type` | VARCHAR(50) | NOT NULL | HOTEL, ROOM_TYPE, TOUR, etc. |
| `url` | VARCHAR(500) | NOT NULL | Link to S3/Cloudinary |
| `is_thumbnail` | BOOLEAN | DEFAULT FALSE | Cover image flag |
| `display_order` | INT | DEFAULT 0 | Sorting position |

## References
- [[database-schema]]
- [[erd-summary]]
