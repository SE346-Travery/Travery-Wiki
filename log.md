# Processing Log

Record of documents processed into the wiki.

## [2026-04-26] Ingest | Business Documentation
- **File**: `raw/Travery/Traver-Docs/Travery - Tài liệu doanh nghiệp.md`
- **Action**: Created [[travery-business-docs]], updated [[travery]], [[tour-tron-goi]], [[xe-khach-tuyen-co-dinh]], [[khach-san]].

## [2026-04-26] Ingest | System Documentation
- **File**: `raw/Travery/Traver-Docs/Travery - Tài liệu nghiệp vụ hệ thống.md`
- **Action**: Created [[travery-system-docs]], added roles and workflows.

## [2026-04-26] Ingest | Dev Rules
- **File**: `raw/Travery/github_cicd_rule.md`
- **Action**: Created [[github-cicd-rules]], extracted CI/CD concepts.

## [2026-04-26] Ingest | Architecture & Codebases
- **Files**: `raw/Travery/Travery.drawio - draw.io.md`, `raw/Travery/Travery-Backend/`, `raw/Travery/Travery-Frontend/`
- **Action**: Created [[drawio-diagrams]], [[travery-backend]], and [[travery-frontend]].
- **Concepts Added**: [[erd-diagram]], [[use-case-diagram]], [[custom-tour]], [[add-on]], [[otp]], [[chat-system]], [[ci-cd-pipeline]], [[conventional-commits]].
- **Roles Added**: [[huong-dan-vien]], [[le-tan]], [[quan-tri-vien]].

## [2026-05-01] Ingest | Technical Deep-Dive
- Created detailed entity pages in `wiki/entities/`:
    - [[User]]
    - [[Tour]]
    - [[TourInstance]]
    - [[TourBooking]]
    - [[TourBookingMember]]
    - [[Vehicle]]
    - [[Driver]]
    - [[Hotel]]
    - [[RefreshToken]]
- Created technical concept pages in `wiki/concepts/`:
    - [[jwt-authentication]]
    - [[otp-management]]
    - [[monitoring-stack]]
- Updated [[index]] with new sections and links.

## [2026-05-06] Ingest | Deployment & Database Deep-Dive
- **Files**: `raw/Travery/DEPLOYMENT_GUIDE.md`, `raw/Travery/Database_Schema.md`, `raw/Travery/ERD_Summary.md`
- **Action**: Created [[deployment-guide]], [[database-schema]], and [[erd-summary]].
- **Concepts Added/Updated**: [[deployment-architecture]], [[git-strategy]], [[branch-protection-rules]], [[docker-dns]], [[monitoring-stack]].
- **Entities Added/Updated**: Comprehensive update of 20+ entity pages including [[User]], [[Tourist]], [[Receptionist]], [[Coordinator]], [[Guide]], [[Admin]], [[Hotel]], [[RoomType]], [[Room]], [[Amenity]], [[HotelService]], [[Tour]], [[TourItinerary]], [[TourInstance]], [[TourBooking]], [[BookingMember]], [[Driver]], [[Station]], [[Route]], [[Coach]], [[CoachSeat]], [[CoachTrip]], [[CoachBooking]], [[CoachTicket]], [[HotelBooking]], [[HotelBookingDetail]], [[RoomAssignment]], [[AddOnOrder]], [[PaymentTransaction]], [[RefundRequest]], [[Review]], [[RefreshToken]], [[Image]], [[ChatSession]].
- Updated [[index]] with comprehensive entity and concept list.

## [2026-05-06] Ingest | System Requirements Specification (SRS)
- **Files**: `raw/Traver-Docs/Travery - Tài liệu nghiệp vụ hệ thống.md`
- **Action**: Formally ingested the Travery-SRS, extracting deep business rules and constraints.
- **Pages Updated**: Enriched [[travery-system-docs]], [[TourBooking]], [[CoachBooking]], [[HotelBooking]], [[TourInstance]], [[RefundPolicy]], [[custom-tour]], [[add-on]], [[ChatSession]], and [[Hotel]] with specific operational parameters (e.g., 15-minute hold times, exact pax limits, refund thresholds, and SLA response times).

## [2026-05-07] Lint | Remove Assignments
- **Action**: Removed `assignments-dev-backend.md` from the wiki to match the deleted raw file (Backend API style doesn't use `/api/v1/`).
- **Pages Updated**: Removed reference from [[index]].

## [2026-05-07] Lint | Fix Dead Links
- **Action**: Scanned the entire wiki for broken `[[links]]`. Re-mapped friendly-name links to proper file slugs (e.g., `[[Custom Tour]]` -> `[[custom-tour]]`, `[[Điều phối viên]]` -> `[[dieu-phoi-vien]]`) and removed formatting for completely unresolvable dead links (e.g., `[[Nginx]]` -> `Nginx`).
- **Pages Updated**: Updated dozens of concept, entity, and organization pages to ensure complete link consistency.

## [2026-05-08] Ingest | Backend Evolution
- **Source**: `raw/Travery-Backend/`
- **Action**: Ingested updates from the backend codebase.
- **Key Changes**: 
    - Updated [[travery-backend]] with Hibernate Search (Lucene), Virtual Threads, and social login dependencies.
    - Created [[Destination]] entity.
    - Updated [[Tour]] to reflect the structural shift from `destination_code` (String) to `destination_id` (FK to Destination).
    - Updated [[index]] with the new entity.
