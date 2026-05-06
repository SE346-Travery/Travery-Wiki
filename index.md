# Travery Wiki Index

Welcome to the internal knowledge base for the **Travery** travel ecosystem.

## 📚 Source Documents
- [[travery-business-docs]] - Business overview and core services.
- [[travery-system-docs]] - Technical requirements and system workflows.
- [[github-cicd-rules]] - Development and CI/CD guidelines.
- [[drawio-diagrams]] - System architecture and schema diagrams.
- [[travery-backend]] - Backend technical stack and infrastructure.
- [[travery-frontend]] - Frontend technical stack and platform support.

## 🏢 Organizations
- [[travery]] - The main enterprise.

## 👥 People & Roles
- [[khach-hang]] - Customer / Tourist role.
- [[dieu-phoi-vien]] - Office management and consultation role.
- [[huong-dan-vien]] - Field execution and guide role.
- [[le-tan]] - Hotel counter management role.
- [[quan-tri-vien]] - System administration role.
- [[hoang-duc-chinh]] - Technical lead / contact point.
- [[Tourist]] - Customer/Client entity.
- [[Receptionist]] - Hotel staff entity.
- [[Coordinator]] - Management staff entity.
- [[Guide]] - Field staff entity.
- [[Admin]] - System administrator entity.

## 🗄 System Entities
- [[User]] - Base user entity and roles.
- [[Tourist]] - Customer/Client entity.
- [[Receptionist]] - Hotel staff entity.
- [[Coordinator]] - Management staff entity.
- [[Guide]] - Field staff entity.
- [[Admin]] - System administrator entity.
- [[Tour]] - Core tour definition and pricing.
- [[TourInstance]] - Specific departures and assignments.
- [[TourBooking]] - Customer bookings and status.
- [[BookingMember]] - Individual members in a booking (Polymorphic).
- [[Vehicle]] - Fleet assets (Bus, Minivan).
- [[Coach]] - Physical bus assets and types.
- [[CoachSeat]] - Seat layout for coaches.
- [[Driver]] - Name, license, and status.
- [[Station]] - Physical terminals and pickup points.
- [[Route]] - Fixed travel paths between stations.
- [[CoachTrip]] - Specific bus departures.
- [[CoachBooking]] - Bus ticket reservations.
- [[Hotel]] - Name, address, and amenities.
- [[RoomType]] - Categories of hotel rooms.
- [[Room]] - Physical room instances.
- [[HotelBooking]] - Hotel reservations.
- [[HotelService]] - Add-on services offered by hotels.
- [[AddOnOrder]] - Specific requests for add-ons.
- [[PaymentTransaction]] - Financial transaction records (Polymorphic).
- [[RefundRequest]] - Customer requests for money back.
- [[Review]] - Unified rating and comment system.
- [[RefreshToken]] - Auth token management.
- [[Image]] - Centralized gallery management.
- [[Amenity]] - Global catalog of features.
- [[ChatSession]] - Consultation and support sessions.

## 📅 Project Management
- [[assignments-dev-backend]] - Optimized task division for 2 developers.

## 💡 Key Services
- [[tour-tron-goi]] - Package travel service.
- [[xe-khach-tuyen-co-dinh]] - Inter-provincial bus service.
- [[khach-san]] - Accommodation service.
- [[custom-tour]] - Personalized travel design.

## 🛠 Technical & Operational Concepts
- [[add-on]] - Supplemental hotel/tour services.
- [[branch-protection-rules]] - Security gates for code integration.
- [[chat-system]] - Real-time consultation and support.
- [[ci-cd-pipeline]] - Automated deployment workflow.
- [[conventional-commits]] - Standardized commit messages.
- [[deployment-architecture]] - Multi-server infrastructure layout.
- [[docker-dns]] - Internal container service discovery.
- [[erd-diagram]] - Database schema modeling.
- [[git-strategy]] - GitHub Flow and branching model.
- [[jwt-authentication]] - JWT flow and security.
- [[monitoring-stack]] - Observability with Alloy, Prometheus, Loki, Grafana.
- [[otp-management]] - OTP generation and verification logic.
- [[use-case-diagram]] - Functional requirement modeling.
