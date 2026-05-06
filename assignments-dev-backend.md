# Phân chia Công việc Phát triển Backend (2 Developers)

Tài liệu này xác định các endpoint chi tiết cho 2 developer nhằm tối ưu hóa khả năng làm việc song song và phân định rõ trách nhiệm theo vòng đời dịch vụ.

---

## 1. Developer A: Trải nghiệm Khách hàng & Sản phẩm
**Trọng tâm:** Các API dành cho khách hàng (Tourist) và thiết lập sản phẩm cho Điều phối viên.

### API Endpoints:

#### A. Khám phá & Tìm kiếm (Public/Tourist)
- `GET /api/v1/tours`: Lấy danh sách tour (hỗ trợ các query params: `search`, `minPrice`, `maxPrice`, `destination`).
- `GET /api/v1/tours/featured`: Lấy danh sách các tour nổi bật/được gợi ý.
- `GET /api/v1/tours/{id}`: Xem chi tiết một tour cụ thể và lịch trình đi kèm.

#### B. Đặt chỗ & Quản lý đơn hàng (Tourist)
- `POST /api/v1/bookings`: Tạo đơn đặt tour mới (xử lý logic giữ chỗ 15 phút, lưu danh sách thành viên).
- `GET /api/v1/bookings/my`: Lấy danh sách các tour vừa đặt/hủy của chính khách hàng đó.
- `GET /api/v1/bookings/{id}`: Xem thông tin chi tiết của một đơn hàng cụ thể.
- `POST /api/v1/bookings/{id}/cancel`: Thực hiện yêu cầu hủy tour và tự động tính toán số tiền hoàn trả theo [[Chính sách hoàn tiền]].
- `POST /api/v1/tours/{id}/reviews`: Gửi đánh giá sao (1-5) và nhận xét sau khi hoàn thành dịch vụ.

#### C. Thiết lập Sản phẩm (Coordinator Setup)
- `POST /api/v1/tours/templates`: Điều phối viên tạo mẫu tour mới (cho phép chọn [[Hotel]], loại phòng, và loại xe [[Vehicle]]).

**Thực thể chính (Entities):** [[Tour]], [[TourBooking]], [[TourBookingMember]], [[Hotel]].

---

## 2. Developer B: Vận hành & Thực thi
**Trọng tâm:** Các API dành cho nhân viên hiện trường (Guide) và công cụ giám sát vận hành cho Điều phối viên.

### API Endpoints:

#### A. Nhiệm vụ Hướng dẫn viên (Guide)
- `GET /api/v1/staff/guide/instances`: Lấy danh sách các tour mà HDV đó được phân công (hỗ trợ lọc: `all`, `ongoing`, `completed`).
- `GET /api/v1/staff/guide/instances/{id}`: Xem chi tiết nhiệm vụ, bao gồm danh sách đoàn, thông tin xe/tài xế và các yêu cầu đặc biệt.
- `PATCH /api/v1/staff/guide/instances/{id}/attendance`: Thực hiện điểm danh thành viên trong đoàn.
- `GET /api/v1/staff/guide/instances/{id}/passengers`: Tìm kiếm nhanh thông tin khách hàng trong đoàn theo Tên hoặc CCCD.
- `PATCH /api/v1/staff/guide/instances/{id}/progress`: Cập nhật các mốc tiến độ thực tế (Đã khởi hành, Đã nhận phòng, Đã kết thúc) theo [[Giám sát hành trình]].
- `POST /api/v1/staff/guide/instances/{id}/incidents`: Báo cáo sự cố phát sinh tại hiện trường về văn phòng.

#### B. Giám sát Vận hành (Coordinator Ops)
- `GET /api/v1/staff/coordinator/instances`: Xem danh sách tất cả các chuyến tour đang/sắp vận hành của toàn hệ thống.
    - Bộ lọc (Filter): `all`, `ongoing`, `completed`, `waiting_confirmation` (đủ 10-30 người), `low_occupancy` (chưa đủ người).
- `GET /api/v1/staff/coordinator/instances/{id}`: Xem trạng thái chi tiết, vị trí và tiến độ của một chuyến đi cụ thể.

**Thực thể chính (Entities):** [[TourInstance]], [[Guide]], [[Driver]], [[Vehicle]].

---

## 3. Lưu ý

1.  **Giai đoạn Đồng bộ (Sync Phase):**
    - Thống nhất cấu trúc Database cho các bảng chung ([[TourBooking]] và [[TourInstance]]).
    - Chốt danh sách các giá trị Enum cho trạng thái (ví dụ: `CONFIRMED`, `IN_PROGRESS`, `NO_SHOW`).
2.  **Hợp đồng API (API Contract):**
    - Sử dụng [[ScalarConfig]] để định nghĩa sớm các DTO và Controller giúp bên còn lại có thể viết code dựa trên cấu trúc dữ liệu mong đợi.
3.  **Dữ liệu giả (Mocking):**
    - Developer B sử dụng SQL script để tạo dữ liệu `TourBooking` giả nhằm kiểm thử các tính năng vận hành mà không cần chờ API đặt chỗ của Developer A.
4.  **Tích hợp (Integration):**
    - Tuân thủ quy trình [[ci-cd-pipeline]], đẩy code lên nhánh `test` thường xuyên để phát hiện sớm các xung đột logic.

---
**Tham chiếu:**
- [[travery-business-docs]]
- [[travery-system-docs]]
- [[erd-diagram]]
