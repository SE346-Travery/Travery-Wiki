---
title: "Destination"
category: entities
tags: [geography, tour]
sources: [travery-backend, database-schema]
updated: 2026-05-08
---

# Entity: Destination

Represents a geographical location or region served by Travery's tours.

## Database Table: `destinations`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `code` | VARCHAR(50) | UNIQUE, NOT NULL | Machine-readable slug (e.g., `da-lat`) |
| `name` | VARCHAR(255) | NOT NULL | Human-readable name (e.g., `Đà Lạt`) |
| `region` | VARCHAR(20) | NOT NULL | Enum: `NORTH`, `CENTRAL`, `SOUTH` |
| `image_url` | VARCHAR(500) | NULL | Representative image for the destination |
| `description` | TEXT | NULL | Detailed description or travel guide |

## Relationships
- **Tour**: One destination can host multiple [[Tour]]s.

## References
- [[travery-backend]]
- [[database-schema]]
