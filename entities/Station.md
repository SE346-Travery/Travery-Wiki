---
title: "Station"
category: entities
tags: [logistics, location]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Station

Physical bus terminals or office locations acting as departure/arrival points.

## Database Table: `stations`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `name` | VARCHAR(255) | NOT NULL | Station name |
| `address` | VARCHAR(500) | NOT NULL | Detailed street address |
| `city_province` | VARCHAR(100) | NOT NULL | Region |
| `latitude/longitude` | DECIMAL | NULL | GPS coordinates |

## Relationships
- **Routes**: Acts as `origin_station_id` or `destination_station_id` for [[Route]] entities.

## References
- [[database-schema]]
