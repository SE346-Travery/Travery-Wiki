# Source: Travery - Tài liệu nghiệp vụ hệ thống.md (Travery-SRS)

## Summary
This document serves as the **System Requirements Specification (SRS)** for the Travery application. It acts as the definitive blueprint for digitizing service bookings, coordination, and customer care, mapping directly to the underlying [[database-schema]].

Key areas covered include:
- **Introduction**: Reinforces Travery's model as a direct service provider.
- **User Roles & Authentication**: Defines roles for [[khach-hang]] (Tourist), [[dieu-phoi-vien]], [[huong-dan-vien]], [[le-tan]], and [[quan-tri-vien]]. It specifies registration via email, [[otp]] verification, and session management.
- **Service Workflows**: Detailed step-by-step logic for booking [[tour-tron-goi]], [[xe-khach-tuyen-co-dinh]], and [[khach-san]]. Highlights strict system constraints (e.g., 10-30 pax limits for tours, 15-minute payment hold locks, 20kg luggage limits for buses).
- **Payment & Failure Handling**:
    - **Hold Time**: 15 minutes for all services.
    - **Failure Modes**: System must handle rejected transactions, connection errors, and callback timeouts (manual confirmation by [[dieu-phoi-vien]] required if callback fails but payment succeeded).
- **Policies & SLAs**:
    - **Confirmation SLAs**: Tour confirmation within **4 business hours** post-payment; Hotel/Coach instant.
    - **Support SLAs**: [[dieu-phoi-vien]] response within **30 minutes** during business hours (8:00–17:30, Mon-Sat).
    - **Refunds**: Processed within **5-7 business days**.
    - **Feedback**: Response to negative reviews within **48 business hours**.
- **Incident Reporting**: A 3-step structured process involving [[huong-dan-vien]] or customers reporting via the app, followed by immediate coordination and status updates via [[chat-system]].
- **Custom Tour Design**: Collaborative process where quotes are valid for **3 days** and requests should be submitted at least **7 days** in advance.

## Identified Entities
- **Organizations**: [[travery]]
- **People/Roles**: [[khach-hang]], [[dieu-phoi-vien]], [[huong-dan-vien]], [[le-tan]], [[quan-tri-vien]]
- Concepts**: [[tour-tron-goi]], [[xe-khach-tuyen-co-dinh]], [[khach-san]], [[RefundPolicy]], No Show-up, [[custom-tour]], [[add-on]], [[otp]], [[chat-system]], [[payment-failure-handling]], [[service-level-agreement]]

