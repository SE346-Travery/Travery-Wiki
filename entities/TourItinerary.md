---
title: "TourItinerary"
category: entities
tags: [asset, detail]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: TourItinerary

A daily breakdown of activities for a [[Tour]].

## Database Table: `tour_itineraries`

| Column        | Data Type    | Constraints  | Description               |
| ------------- | ------------ | ------------ | ------------------------- |
| `id`          | UUID         | PK           | Unique identifier         |
| `tour_id`     | UUID         | FK(tours.id) | Parent tour template      |
| `day_number`  | INT          | NOT NULL     | Sequence (Day 1, 2, etc.) |
| `title`       | VARCHAR(255) | NOT NULL     | Summary of the day        |
| `description` | TEXT         | NOT NULL     | Full activity details     |

## Relationships
- **Parent**: Links to one [[Tour]] template.

## References
- [[database-schema]]
- [[tour-tron-goi]]
