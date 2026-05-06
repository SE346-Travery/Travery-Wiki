---
title: "PaymentTransaction"
category: entities
tags: [finance, transaction]
sources: [database-schema, erd-summary]
updated: 2026-05-06
---

# Entity: PaymentTransaction

Polymorphic transaction record for all cash flows.

## Database Table: `payment_transactions`

| Column | Data Type | Constraints | Description |
|---|---|---|---|
| `id` | UUID | PK | Unique identifier |
| `user_id` | UUID | FK(users.id) | Payer |
| `booking_id` | UUID | NOT NULL | Target ID (Poly) |
| `booking_type` | VARCHAR(50) | NOT NULL | TOUR_BOOKING, HOTEL_BOOKING, COACH_BOOKING, ADD_ON_ORDER |
| `amount` | DECIMAL(12,2) | NOT NULL | Value |
| `transaction_type` | VARCHAR(50) | DEFAULT 'PAYMENT' | PAYMENT, REFUND |
| `payment_method` | VARCHAR(50) | NOT NULL | VNPAY, MOMO, CASH |
| `gateway_trans_id` | VARCHAR(255) | NULL | Provider reference |
| `status` | VARCHAR(50) | NOT NULL | SUCCESS, FAILED, PENDING |
| `paid_at` | TIMESTAMP | NULL | Success timestamp |

## Relationships
- **Parent**: Links polymorphically to various booking tables.
- **Refund**: Source for [[RefundRequest]].

## References
- [[database-schema]]
- [[erd-summary]]
