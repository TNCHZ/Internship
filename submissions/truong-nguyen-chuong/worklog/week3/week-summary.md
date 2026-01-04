# 📊 Tổng kết Tuần 3 – Thực tập Backend / Fullstack (09/11 – 14/11/2025)

## 📅 Thông tin chung
- **Tuần thực tập**: 3/9  
- **Thời gian**: 09/11/2025 – 14/11/2025  
- **Tổng thời gian làm việc**: ~24 giờ  
- **Vai trò chính**: Backend Developer (User Service) – kết nối Frontend Authentication  
- **Mood tổng quan**: 😊 → 😄  
  > Từ áp lực thiết kế & họp nhóm → tự tin khi hệ thống bắt đầu chạy end-to-end

---

## 🎯 Mục tiêu tuần
- [x] Chốt kiến trúc & phạm vi **User Service**
- [x] Hoàn thiện **API specification & DTO design**
- [x] Tích hợp **Redis (OTP)** và **Email Service**
- [x] Thiết kế & test **Authentication flow end-to-end (Backend ↔ Frontend)**
- [x] Xây dựng nền tảng cho các flow tiếp theo: OTP, reset password, refresh token

---

## 💼 Tổng hợp công việc đã thực hiện

### 1️⃣ Thiết kế kiến trúc & dẫn dắt technical discussion
- Trình bày và bảo vệ:
  - Kiến trúc **microservices**
  - Database design cho **User Service**
- Làm rõ **boundary & responsibility** của User Service:
  - Authentication, identity, OTP, email verification
  - Không xử lý business logic của Event / Notification
- Thống nhất:
  - API versioning (`/api/v1`)
  - RESTful conventions
  - Định hướng API Guidelines chung cho toàn hệ thống

📌 **Giá trị tạo ra**:  
Thiết kế được chốt sớm → giảm rủi ro refactor lớn về sau.

---

### 2️⃣ Hoàn thiện API Specification & DTO Design
- Thiết kế đầy đủ các endpoint:
  - Register / Login
  - Verify Email (OTP)
  - Forgot / Reset Password
  - Update User Profile
- Chuẩn hóa:
  - HTTP status codes
  - Error response format
- Thiết kế DTO rõ ràng:
  - Request DTO ≠ Response DTO
  - Không expose entity
  - Áp dụng validation (`@Valid`, `@Email`, `@Size`, …)

📌 **Giá trị tạo ra**:  
Frontend có thể làm việc độc lập ngay khi backend chưa implement xong.

---

### 3️⃣ Tích hợp Redis & Email Service (Backend)
- **Redis**:
  - Lưu OTP (TTL 5 phút)
  - Retry limit & rate limiting
  - Không lưu trạng thái tạm trong database
- **Email Service**:
  - Java Mail Sender (Gmail SMTP)
  - App Password, không hardcode secret
  - Thiết kế service reusable
- Test thực tế:
  - Redis TTL
  - Gửi email thật

📌 **Giá trị tạo ra**:  
Authentication flow có đầy đủ nền tảng kỹ thuật để triển khai production-ready.

---

### 4️⃣ Kết nối Frontend ↔ Backend Authentication
- Thiết kế UI/UX:
  - Login
  - Logout
  - Session expired
- Kết nối API:
  - `POST /api/v1/auth/login`
  - Lưu & attach JWT
- Xử lý:
  - Axios interceptor
  - 401 → auto logout
- Test end-to-end:
  - Login đúng / sai
  - Token hết hạn
  - Logout

📌 **Giá trị tạo ra**:  
Authentication **chạy thật**, không chỉ dừng ở thiết kế.

---

## 📚 Kiến thức & kỹ năng đạt được

### 🔧 Kỹ thuật
- Spring Boot:
  - Redis integration
  - Email integration
  - Validation & DTO design
- Authentication:
  - JWT lifecycle
  - OTP flow
  - Stateless auth
- Frontend:
  - JWT handling
  - Axios interceptors
  - Protected routes (concept)

### 💡 System Design
- Service boundary & responsibility
- Trade-off security ↔ usability
- API-first development

### 🤝 Soft Skills
- Technical leadership
- Facilitation & negotiation
- Communication giữa backend ↔ frontend

---

## 🚧 Khó khăn tiêu biểu & cách giải quyết

### Vấn đề 1: Chưa thống nhất phạm vi User Service
- **Giải pháp**:
  - Làm rõ scope ngay trong buổi họp
  - Document rõ “User Service làm gì & không làm gì”
- **Kết quả**: Team đồng thuận, kiến trúc được chốt

---

### Vấn đề 2: Lỗi auth khi tích hợp frontend
- **Nguyên nhân**: Quên attach JWT header
- **Giải pháp**: Axios interceptor toàn cục
- **Bài học**: Auth logic cần centralized

---

## 💭 Nhận thức & bài học quan trọng

- **Technical Insight**:  
  > Thiết kế tốt giúp coding nhanh hơn gấp nhiều lần.
- **Project Insight**:  
  > API design là “hợp đồng” giữa các team.
- **Self Insight**:  
  > Phù hợp với vai trò Technical Lead / System Designer trong tương lai.

---

## 📈 Đánh giá tổng thể tuần 3

| Tiêu chí | Đánh giá |
|--------|---------|
| Năng suất | (8.5/10) |
| Học hỏi | (9/10) |
| Hợp tác |  (8/10) |
| Tổng thể | (8.5/10) |

---

## 🚀 Định hướng tuần 4
- Implement:
  - OTP verification frontend
  - Reset password flow
  - Refresh token
- Hoàn thiện:
  - Protected routes
  - Auth guards
- Chuẩn bị:
  - Integration tests
  - Refactor auth logic thành reusable modules

---

**🎯 Tiến độ dự án sau Tuần 3:**  
**~60% User Service Authentication**

---

_Worklog summary by: Trương Nguyên Chương_  
_Week reviewed: Tuần 3_
