# Weekly Summary – Tuần 1 (26/10/2025 – 01/11/2025)

---

## 📅 Thông tin tổng quan
- **Thời gian**: 26/10/2025 – 01/11/2025  
- **Tuần thực tập**: Tuần 1  
- **Tổng thời gian học & thực hành**: ~28 giờ  
- **Trọng tâm**:  
  - Cloud Computing fundamentals  
  - AWS core services (VPC, EC2, S3, IAM)  
  - Kiến trúc mạng và bảo mật cơ bản trên AWS  

---

## 🎯 Mục tiêu tuần
- Làm quen với nền tảng AWS và giao diện Management Console
- Hiểu rõ các khái niệm cloud cốt lõi và mô hình dịch vụ
- Nắm vững kiến trúc mạng AWS thông qua VPC
- Thực hành triển khai EC2, S3, IAM theo best practices
- Hình thành tư duy thiết kế hệ thống cloud có cấu trúc

---

## 🧩 Tổng hợp công việc đã thực hiện

### 1️⃣ Cloud Computing Fundamentals
- Hiểu sự khác biệt giữa **On-Premise vs Cloud**
- Phân biệt rõ **IaaS – PaaS – SaaS**
- Nắm được mô hình **Shared Responsibility Model**
- Nhận thức được lợi ích về **cost (CAPEX → OPEX), scalability, availability**

👉 **Ý nghĩa**:  
Đây là bước nền tảng giúp định hình tư duy đúng trước khi tiếp cận các dịch vụ kỹ thuật cụ thể.

---

### 2️⃣ Làm quen AWS Global Infrastructure
- Tìm hiểu **Regions, Availability Zones, Edge Locations**
- Lựa chọn region **ap-southeast-1 (Singapore)** phù hợp với:
  - Latency thấp cho Việt Nam
  - Đầy đủ dịch vụ
  - Chi phí hợp lý

👉 **Nhận thức quan trọng**:  
Việc chọn region ảnh hưởng trực tiếp đến **hiệu năng, chi phí và kiến trúc hệ thống**.

---

### 3️⃣ VPC – Nền tảng của mọi hệ thống AWS
- Tạo VPC bằng Wizard và **tự cấu hình VPC thủ công**
- Chia **public subnet / private subnet**
- Cấu hình:
  - Internet Gateway
  - NAT Gateway
  - Route Tables
- Hiểu rõ luồng traffic:
  - Public subnet → IGW → Internet
  - Private subnet → NAT Gateway → Internet

👉 **Ý nghĩa học được**:  
Tự cấu hình VPC giúp hiểu sâu bản chất networking, thay vì phụ thuộc vào Wizard.

---

### 4️⃣ EC2 – Compute cơ bản
- Tìm hiểu instance types, AMI, pricing models
- Launch EC2 trong public subnet
- Kết nối SSH qua key pair
- Hiểu vai trò của:
  - Public IP / Elastic IP
  - Security Group
- Debug các lỗi SSH phổ biến

👉 **Bài học quan trọng**:  
EC2 chỉ hoạt động đúng khi **network + security + routing** được cấu hình chính xác.

---

### 5️⃣ S3 – Object Storage
- Hiểu S3 là **object storage**, không phải block storage
- Thực hành:
  - Tạo bucket
  - Upload / download file
  - Versioning & encryption
- Tìm hiểu các **S3 Storage Classes** và use cases

👉 **Nhận thức**:  
S3 không chỉ là nơi lưu file, mà là nền tảng cho rất nhiều dịch vụ AWS khác.

---

### 6️⃣ IAM – Nền tảng bảo mật
- Hiểu rõ:
  - Users, Groups, Roles, Policies
  - Authentication vs Authorization
- Thực hành:
  - Tạo IAM user
  - Gán group-based permissions
  - Enable MFA
- Áp dụng **principle of least privilege**

👉 **Bài học cốt lõi**:  
IAM là trái tim của security trên AWS – sai IAM có thể dẫn đến rủi ro nghiêm trọng.

---

## 📚 Kiến thức & kỹ năng đạt được

### 🔧 Kỹ năng kỹ thuật
- AWS: VPC, EC2, S3, IAM
- Cloud Networking: CIDR, subnetting, routing
- Security: Security Group, NACL, IAM policies
- Linux basics & SSH troubleshooting

### 💡 Kiến thức nền tảng
- Kiến trúc mạng chuẩn cho hệ thống backend
- Phân biệt rõ public vs private workload
- Tư duy thiết kế hệ thống cloud theo lớp (network → compute → storage → security)

### 🤝 Kỹ năng mềm
- Tự học qua documentation chính thức
- Ghi chép có hệ thống
- Phân tích và debug vấn đề theo luồng logic

---

## 🚧 Khó khăn nổi bật trong tuần
- Nhầm lẫn giữa Internet Gateway và NAT Gateway
- Chưa quen với CIDR notation
- Lỗi SSH do cấu hình Security Group chưa chính xác
- IAM policies dễ sai cú pháp và cấp quyền quá rộng

👉 **Cách khắc phục**:
- Vẽ sơ đồ kiến trúc trước khi triển khai
- Đọc kỹ AWS documentation
- Thực hành lại nhiều lần thay vì chỉ xem lý thuyết

---

## 💭 Tổng kết & Nhận thức sau tuần 1
- AWS không khó, nhưng **đòi hỏi tư duy hệ thống**
- Networking và security là nền móng, không thể bỏ qua
- Làm thủ công giúp hiểu sâu hơn rất nhiều so với dùng công cụ tự động
- Việc học cloud cần đi từ **bản chất → thực hành → rút ra quy luật**

---

## 📈 Đánh giá tổng thể tuần

| Tiêu chí | Đánh giá |
|--------|---------|
| Mức độ hoàn thành mục tiêu | ⭐⭐⭐⭐☆ (80%) |
| Kiến thức đạt được | ⭐⭐⭐⭐⭐ |
| Thực hành | ⭐⭐⭐⭐☆ |
| Tư duy hệ thống | ⭐⭐⭐⭐☆ |
| Mức độ hài lòng | ⭐⭐⭐⭐☆ |

---

## 📋 Định hướng cho tuần tiếp theo (Tuần 2)
- Thực hành EC2 trong **private subnet**
- Áp dụng mô hình **Bastion Host**
- Tìm hiểu:
  - Load Balancer
  - Auto Scaling
- Bắt đầu liên hệ kiến thức AWS với **microservices architecture**

---

_Weekly Summary created by: Trương Nguyên Chương_  
_Period reviewed: 26/10/2025 – 01/11/2025_
