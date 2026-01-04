# Weekly Summary - Tuần 2 (02/11 - 08/11/2025)

## 📊 Tổng quan tuần
- **Tuần thực tập**: 2/9
- **Giai đoạn**: Phân tích Yêu cầu & Thiết kế Đồ án (02/11 - 26/11/2025)
- **Mục tiêu tuần**: Hoàn thành phân tích, thiết kế kiến trúc User Service và chuẩn bị nền tảng kỹ thuật
- **Tiến độ so với mục tiêu tuần**: 100% - Đạt được tất cả mục tiêu đề ra

## 🎯 Các mục tiêu đã hoàn thành
- [x] Họp nhóm khởi động đồ án, chốt chuyển đổi sang kiến trúc Microservices (02/11)
- [x] Thiết kế ERD cho User Service theo mô hình Database-per-Service (03/11)
- [x] Thiết kế API specification cho User Service (04/11)
- [x] Thiết kế Redis schema cho OTP (05/11)
- [x] Thiết kế chức năng gửi email với Java Mail Sender (06/11)
- [x] Khởi tạo project User Service với Spring Boot (07/11)
- [x] Cấu hình Spring Security với JWT và tạo JPA Entities (08/11)

## 💼 Công việc đã thực hiện
### 1. Phân tích và Thiết kế Kiến trúc
- **Họp nhóm (02/11)**: Thuyết phục nhóm chuyển từ Monolithic sang Microservice, thống nhất chia hệ thống thành 4 service (User, Event, Notification, Page + AIChat). User Service được chọn làm service đầu tiên.
- **Thiết kế Database (03/11)**: Tạo ERD chi tiết cho User Service với các bảng: account, account_disable, user_profile, admin_profile. Áp dụng các best practices: UUID v7, tách biệt identity và profile, sử dụng JSONB cho dữ liệu linh hoạt.
- **Thiết kế API (04/11)**: Thiết kế 8 endpoints cho User Service, chia thành 2 nhóm: Public APIs (authentication) và Authenticated APIs (self-management). Sử dụng OpenAPI 3.0 để đặc tả.
- **Thiết kế Redis cho OTP (05/11)**: Thiết kế cấu trúc lưu trữ OTP đơn giản với TTL 5 phút, phù hợp cho giai đoạn đầu.
- **Thiết kế Email Service (06/11)**: Phân tích luồng gửi email cho OTP và quên mật khẩu, thiết kế EmailService tách biệt với business logic.

### 2. Thiết lập Nền tảng Kỹ thuật
- **Khởi tạo Project (07/11)**: Tạo Spring Boot project với các dependencies cần thiết (Web, Data JPA, Redis, Security, Validation, Mail). Cấu hình Docker Compose cho PostgreSQL và Redis.
- **Cấu hình Spring Security & JWT (08/11)**: Cài đặt JWT authentication filter, cấu hình SecurityConfig, tạo JPA Entities từ ERD.

### 3. Công cụ và Quy trình
- Sử dụng Draw.io cho sơ đồ kiến trúc
- Sử dụng Notion để ghi chú và tài liệu hóa
- Thiết lập Git repository với cấu trúc project rõ ràng
- Áp dụng Docker cho môi trường phát triển nhất quán

## 📚 Kiến thức học được
### 🔧 Kỹ năng kỹ thuật
- **Microservices Architecture**: Hiểu sâu về cách chia service theo business capability, pattern Database-per-Service
- **Database Design**: Thiết kế schema cho service nhỏ, sử dụng UUID v7, JSONB, check constraints
- **API Design**: RESTful API best practices, OpenAPI specification, versioning strategy
- **Spring Boot**: Spring Security 6.x với JWT, Spring Data JPA, Redis integration
- **DevOps**: Docker Compose cho multi-service development environment

### 💡 Khái niệm và Lý thuyết
- **Distributed Systems**: Saga pattern cho distributed transactions, challenges của microservices
- **Security**: JWT authentication flow, password hashing với Argon2id, OTP best practices
- **Software Design**: Separation of concerns, layered architecture, clean code principles

### 🤝 Kỹ năng mềm
- **Thuyết trình**: Trình bày technical proposal, giải thích complex concepts cho team
- **Lãnh đạo**: Dẫn dắt technical decision, thuyết phục team về kiến trúc mới
- **Giải quyết vấn đề**: Phân tích root cause, debug complex framework issues

## 🚧 Khó khăn và Giải pháp
### 1. Distributed Transactions trong Microservices
- **Khó khăn**: Thành viên lo ngại về data consistency khi chuyển từ Monolithic (ACID transactions) sang Microservices (distributed transactions)
- **Giải pháp**: Giới thiệu Saga pattern, đề xuất bắt đầu với User Service đơn giản, cam kết nghiên cứu thêm

### 2. Thiết kế Database cho User Service
- **Khó khăn**: Cân nhắc giữa soft delete (deleted_at) vs hard delete với bảng account_disable
- **Giải pháp**: Chọn hard delete với bảng account_disable để tăng security và simplify authentication logic

### 3. Cấu hình Spring Security 6.x
- **Khó khăn**: Migration từ Spring Security 5.x (WebSecurityConfigurerAdapter) lên 6.x (SecurityFilterChain bean)
- **Giải pháp**: Đọc documentation kỹ, tham khảo migration guide, debug từng bước

### 4. Ranh giới giữa Public và Authenticated APIs
- **Khó khăn**: Xác định API nào nên public, API nào cần authentication
- **Giải pháp**: Phân loại rõ ràng theo nguyên tắc "self-managed user", whitelist public APIs

## 💭 Bài học kinh nghiệm
### Thành công
1. **Chuẩn bị kỹ tài liệu** trước cuộc họp giúp thuyết phục team dễ dàng hơn
2. **Thiết kế tỉ mỉ** từ đầu tiết kiệm thời gian sửa chữa sau này
3. **Sử dụng Docker Compose** ngay từ đầu tạo môi trường phát triển nhất quán

### Cần cải thiện
1. **Ước lượng thời gian**: Đôi khi mất nhiều thời gian hơn dự kiến cho việc debug (Spring Security)
2. **Chia sẻ kiến thức**: Nên chia sẻ sớm hơn với team để cùng học hỏi
3. **Testing**: Cần viết test song song với development, không để cuối tuần

## 📈 Đánh giá tuần
### Tiến độ dự án
- **Thiết kế**: Hoàn thành 100%
- **Coding**: Bắt đầu được 20% (setup project, security, entities)
- **Documentation**: Hoàn thành 80%

### Kỹ năng phát triển
- **Technical Skills**: Tăng từ 6/10 lên 8/10 (hiểu sâu về microservices, Spring Security)
- **Soft Skills**: Tăng từ 7/10 lên 8/10 (thuyết trình, lãnh đạo kỹ thuật)
- **Productivity**: 8/10 (hoàn thành đúng hạn, output chất lượng)

## 📋 Kế hoạch tuần tới (Tuần 3: 09/11 - 15/11)
### Mục tiêu chính
1. **Hoàn thiện Coding cho User Service** (đăng ký, đăng nhập, OTP, quên mật khẩu)
2. **Tích hợp với Redis và Email Service**
3. **Viết Unit Tests và Integration Tests**
4. **Review code với team**

### Công việc cụ thể
- **09/11**: Họp nhóm review thiết kế, phân công công việc chi tiết
- **10-12/11**: Implement các endpoints chính (register, login, verify OTP)
- **13-14/11**: Implement forgot password, change password, update profile
- **15/11**: Viết tests, tối ưu code, chuẩn bị demo

### Mục tiêu học tập
- Học về Spring Boot Testing (@WebMvcTest, @DataJpaTest, Testcontainers)
- Tìm hiểu về CI/CD pipeline với GitHub Actions
- Nghiên cứu thêm về monitoring với Spring Boot Actuator

## 🎯 Tự đánh giá tuần
- **Năng suất**: 8.5/10
- **Chất lượng công việc**: 9/10
- **Hợp tác nhóm**: 8/10
- **Học hỏi**: 9/10
- **Tổng thể**: 8.5/10

**Điểm mạnh**: Tư duy hệ thống tốt, khả năng thiết kế chi tiết, kiên trì giải quyết vấn đề phức tạp  
**Điểm cần cải thiện**: Ước lượng thời gian, chia sẻ kiến thức sớm hơn với team

---
*Weekly summary created by: Trương Nguyên Chương*  
*Next weekly review: 15/11/2025*