---
title: "Guide"
category: entities
tags: [user, role, staff]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Guide

Field-based staff who interact directly with customers during tours.

## Database Table: `guides`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK, FK(users.id) | Link to base user |
| `employee_code` | VARCHAR(50) | UNIQUE, NOT NULL | Internal ID |
| `guide_license` | VARCHAR(100) | UNIQUE, NOT NULL | Certification ID |
| `languages` | JSONB | DEFAULT '[]' | Languages spoken |
| `years_experience`| INT | DEFAULT 0 | Seniority |

## Relationships
- **Base**: Inherits from [[User]].
- **Assignments**: Assigned to lead [[TourInstance]] departures.

## References
- [[database-schema]]
- [[huong-dan-vien]]
