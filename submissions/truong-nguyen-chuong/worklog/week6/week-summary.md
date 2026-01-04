# Weekly Summary – Tuần 6 (30/11/2025 – 06/12/2025)

---

## 📅 Thông tin tổng quan
- **Thời gian**: 30/11/2025 – 06/12/2025
- **Tuần thực tập**: Tuần 6
- **Tổng thời gian học & thực hành**: ~28 giờ
- **Trọng tâm**:
  - Docker & ECR (deployment basics)
  - IAM fundamentals và authentication flow
  - CDN & caching (Amazon CloudFront)
  - DNS & routing (Route 53)
  - Load balancing (Application Load Balancer)

---

## 🎯 Mục tiêu tuần
- Hiểu và thực hành **IAM** với AWS CLI để hỗ trợ deployment
- Push Docker image vào **ECR** và chuẩn bị cho CI/CD
- Học **CloudFront** (cache strategy, cost) và test cache behavior
- Thực hành **Route 53** (routing policies, health checks, failover)
- Nắm **ALB**: listeners, rules, target groups, health checks

---

## 🧩 Tổng hợp công việc đã thực hiện

### 1️⃣ ECR & IAM (30/11 – 01/12)
- Tìm hiểu flow Docker → ECR (login token, tag, push)
- Debug lỗi: `no basic auth credentials` và `ecr:InitiateLayerUpload`
- Ôn lại IAM fundamentals: User vs Role, Permission vs Trust policy
- Sửa lỗi bằng cách cập nhật **policy** (`AmazonEC2ContainerRegistryFullAccess`) và đảm bảo **region** đúng

👉 **Kết quả**: Push image `user-service` lên ECR thành công và rút ra checklist triển khai (region, permissions, login)

---

### 2️⃣ CDN & Caching (02/12 – 03/12)
- Nghiên cứu CloudFront: Edge locations, origin types (S3/ALB)
- Học cache behavior: Cache Key, TTL (Default/Min/Max), Cache-Control headers
- Phân tích chi phí: data egress vs cache hit ratio
- Soạn plan pre-lab: setup distribution, test cache-hit, invalidation strategy

👉 **Kết quả**: Hiểu rõ trade-offs performance vs cost; có checklist để đo cache efficiency

---

### 3️⃣ DNS & Routing (04/12 – 05/12)
- Ôn lại DNS basics: A/CNAME/NS records, authoritative vs recursive
- Nghiên cứu Route 53 routing policies: simple, weighted, latency-based, failover, geo
- Thiết lập health checks & kịch bản failover, test plan với `dig`/`nslookup`
- Soạn checklist test: low TTL dev zone, simulate primary down, measure time-to-switch

👉 **Kết quả**: Có hiểu biết thực tế về DNS-driven HA & DR và test plan cụ thể

---

### 4️⃣ Load Balancing (06/12)
- Tìm hiểu ALB: listeners, listener rules (path/host), target groups, health checks
- So sánh ALB vs NLB và chọn use-case phù hợp
- Soạn checklist pre-lab: tạo ALB, register targets (v1/v2), simulate unhealthy target, observe CloudWatch metrics

👉 **Kết quả**: Nắm được ALB là trung tâm routing cho microservices và chuẩn bị lab thực hành

---

## 📚 Kiến thức & kỹ năng đạt được

### 🔧 Kỹ năng kỹ thuật
- IAM fundamentals, permission debugging
- Docker ↔ ECR: login token flow, tagging, pushing images
- CDN: CloudFront caching, TTL, cost vs performance trade-offs
- DNS & Route 53: routing policies, health checks, failover testing
- Load balancing: ALB listener rules, target groups, health check strategy

### 💡 Kiến thức nền tảng
- Hiểu authentication flow AWS CLI → IAM → service
- Kiến trúc entry point: DNS → CDN → LB → services
- Design checklist & test plans before thực hành (reduce trial/error)

### 🤝 Kỹ năng mềm
- Structured debugging (root-cause, hypothesis-driven)
- Documenting findings and creating reusable checklists
- Planning lab tests and measuring results

---

## 🚧 Khó khăn nổi bật trong tuần
- IAM permissions phức tạp, dễ gây lỗi deployment
- Thiếu môi trường multi-region để test failover thực tế
- DNS propagation chậm → test failover khó nhanh chóng
- Chưa có full CI/CD pipeline để tự động hóa push → cần hoàn thiện

👉 **Cách khắc phục**:
- Dùng dev hosted zone với TTL thấp để test nhanh
- Sink time vào mô phỏng (scripts) và viết example workflows
- Hoàn thiện GitHub Actions pipeline cho ECR push

---

## 💭 Tổng kết & Nhận thức sau tuần 6
- Tuần này tập trung vào **deployment flow** hơn là chỉ lý thuyết service: hiểu từ IAM → ECR → CDN → DNS → ALB
- Việc soạn checklist và test plan trước khi thực hành giúp debug nhanh và tái sử dụng cho CI/CD
- Multi-layer architecture (DNS → CDN → LB → services) rõ ràng và cần test từng tầng riêng trước khi tích hợp

---

## 📈 Đánh giá tổng thể tuần

| Tiêu chí | Đánh giá |
|--------|---------|
| Mức độ hoàn thành mục tiêu | ⭐⭐⭐⭐☆ (80%) |
| Kiến thức đạt được | ⭐⭐⭐⭐⭐ |
| Thực hành | ⭐⭐⭐⭐☆ |
| Tư duy hệ thống | ⭐⭐⭐⭐⭐ |
| Mức độ hài lòng | ⭐⭐⭐⭐☆ |

---

## 📋 Định hướng cho tuần tiếp theo (Tuần 7)
- Hoàn thiện **CI/CD**: GitHub Actions để tự động build + push image lên ECR
- Thực hành lab: CloudFront distribution + cache-hit testing
- Tạo hosted zone dev và simulate Route 53 failover tests
- Deploy sample service behind ALB and test listener rules + health checks

---

_Weekly Summary created by: Trương Nguyên Chương_
_Period reviewed: 30/11/2025 – 06/12/2025_  