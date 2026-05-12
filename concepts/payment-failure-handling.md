---
title: "Payment Failure Handling"
category: concepts
tags: [technical, finance, error-handling]
sources: [travery-system-docs]
updated: 2026-05-12
---

# Concept: Payment Failure Handling

The system must gracefully handle various failure modes during the transaction process to protect both the customer experience and service inventory.

## Common Scenarios

### 1. Direct Rejection
- **Cause**: Insufficient funds, expired card, or bank refusal.
- **Handling**: The app displays a specific error message. The 15-minute lock on spots/rooms remains active, allowing the customer to attempt payment again with a different method.

### 2. Session Timeout
- **Cause**: Customer fails to complete payment within the 15-minute window.
- **Handling**: The system automatically releases the held inventory and marks the booking as `CANCELLED` or `EXPIRED`.

### 3. Connection Errors
- **Cause**: Network failure during the transaction.
- **Handling**: The app must query the payment gateway for the latest transaction status before displaying a final result to the user. No booking is confirmed without a successful response.

### 4. Callback/Webhook Timeouts
- **Cause**: The payment gateway successfully processes the payment but fails to notify the Travery backend (e.g., due to network lag).
- **Handling**: 
    - The booking remains in a `PENDING` state.
    - The customer is advised to contact a [[dieu-phoi-vien]] via the [[chat-system]] with proof of transaction.
    - The [[dieu-phoi-vien]] can manually verify and confirm the booking in the admin panel.

## References
- [[travery-system-docs]]
- [[PaymentTransaction]]
- [[service-level-agreement]]
