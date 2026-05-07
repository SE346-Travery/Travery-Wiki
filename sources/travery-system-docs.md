# Source: Travery - Tài liệu nghiệp vụ hệ thống.md (Travery-SRS)

## Summary
This document serves as the **System Requirements Specification (SRS)** for the Travery application. It acts as the definitive blueprint for digitizing service bookings, coordination, and customer care, mapping directly to the underlying [[database-schema]].

Key areas covered include:
- **Introduction**: Reinforces Travery's model as a direct service provider.
- **User Roles & Authentication**: Defines roles for [[khach-hang]] (Tourist), [[dieu-phoi-vien]], [[huong-dan-vien]], [[le-tan]], and [[quan-tri-vien]]. It specifies registration via email, [[otp]] verification, and session management.
- **Service Workflows**: Detailed step-by-step logic for booking [[tour-tron-goi]], [[xe-khach-tuyen-co-dinh]], and [[khach-san]]. Highlights strict system constraints (e.g., 10-30 pax limits for tours, 15-minute payment hold locks, 20kg luggage limits for buses).
- **Policies**: Digitized [[RefundPolicy]] and No Show-up logic for automated calculations (e.g., 7-day, 3-6 day, <3 day thresholds).
- **Chat & Consultations**: Describes the real-time [[chat-system]] used for general support (30-min SLA) and the collaborative design of [[custom-tour]]s (quotes valid for 3 days).
- **Technical Procedures**: Incident reporting, payment failure handling (e.g., callback timeouts), and automated 1-day reminders.

## Identified Entities
- **Organizations**: [[travery]]
- **People/Roles**: [[khach-hang]], [[dieu-phoi-vien]], [[huong-dan-vien]], [[le-tan]], [[quan-tri-vien]]
- **Concepts**: [[tour-tron-goi]], [[xe-khach-tuyen-co-dinh]], [[khach-san]], [[RefundPolicy]], No Show-up, [[custom-tour]], [[add-on]], [[otp]], [[chat-system]]
