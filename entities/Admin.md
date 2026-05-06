---
title: "Admin"
category: entities
tags: [user, role, staff]
sources: [database-schema]
updated: 2026-05-06
---

# Entity: Admin

System administrators with oversight of the entire platform.

## Database Table: `admins`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK, FK(users.id) | Link to base user |

## Relationships
- **Base**: Inherits from [[User]].
- **Control**: Manages all staff accounts and system-wide configurations.

## References
- [[database-schema]]
- [[quan-tri-vien]]
