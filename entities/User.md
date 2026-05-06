---
title: "User"
category: entities
tags: [auth, base]
sources: [database-schema, travery-system-docs]
updated: 2026-05-06
---

# Entity: User

The base entity representing any individual in the Travery system. It uses a **Table-per-Type (Joined Inheritance)** strategy to support specialized roles.

## Database Table: `users`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `email` | VARCHAR(255) | UNIQUE, NULL | Login email |
| `password_hashed` | VARCHAR(255) | NULL | Hashed password |
| `full_name` | VARCHAR(100) | NOT NULL | Legal name |
| `phone_number` | VARCHAR(20) | UNIQUE, NULL | Contact number |
| `avatar_url` | VARCHAR(500) | NULL | Profile image link |
| `role` | VARCHAR(50) | NOT NULL | [[UserRoles]] (TOURIST, ADMIN, etc.) |
| `auth_provider` | VARCHAR(20) | NOT NULL | Enum: LOCAL, GOOGLE |
| `cometchat_uid` | VARCHAR(100) | UNIQUE, NULL | Integration ID for CometChat |
| `status` | VARCHAR(20) | DEFAULT 'PENDING' | PENDING, ACTIVE, BANNED |

## Relationships
- **Inheritance**: Sub-typed by [[Tourist]], [[Receptionist]], [[Coordinator]], [[Admin]], and [[Guide]].
- **Session**: Linked to [[RefreshToken]] for auth management.
- **Transactions**: Linked to [[PaymentTransaction]], [[RefundRequest]], and [[Review]].

## References
- [[database-schema]]
- [[jwt-authentication]]
