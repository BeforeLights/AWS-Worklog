---
title: "Sự kiện 4"
date: "2025-11-29"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Báo cáo Tóm tắt: “AWS Cloud Mastery Series #3: AWS Well-Architected – Security Pillar Workshop”

## Tổng quan Sự kiện

Phiên thứ ba của chuỗi AWS Cloud Mastery tập trung vào **AWS Well-Architected Framework**, cụ thể là **Trụ cột Bảo mật (Security Pillar)**. Hội thảo này cung cấp cho người tham dự cái nhìn sâu sắc về năm lĩnh vực chính của bảo mật đám mây: Quản lý Danh tính và Truy cập (IAM), Phát hiện và Giám sát Liên tục, Bảo vệ Cơ sở hạ tầng, Bảo vệ Dữ liệu, và Ứng phó Sự cố. Sự kiện cũng giới thiệu sáng kiến AWS Cloud Club, nhằm mục đích thúc đẩy các kỹ năng điện toán đám mây và xây dựng một cộng đồng vững mạnh các chuyên gia đám mây.

---

## Mục tiêu Sự kiện

Hội thảo nhằm đạt được các mục tiêu sau:
- Giới thiệu sáng kiến AWS Cloud Club và lợi ích của nó đối với sinh viên và chuyên gia.
- Cung cấp sự hiểu biết chi tiết về **năm trụ cột của bảo mật đám mây**:
  1. Quản lý Danh tính và Truy cập (IAM)
  2. Phát hiện và Giám sát Liên tục
  3. Bảo vệ Cơ sở hạ tầng
  4. Bảo vệ Dữ liệu
  5. Ứng phó Sự cố
- Chia sẻ các thực tiễn tốt nhất để triển khai các biện pháp bảo mật trên AWS.
- Nêu bật các trường hợp sử dụng thực tế và các giải pháp bảo mật tiên tiến.

---

## Diễn giả

Sự kiện có sự tham gia của một nhóm đa dạng các AWS Cloud Club Captains, AWS Community Builders, và các chuyên gia trong ngành, bao gồm:
- **Le Vu Xuan An** – AWS Cloud Club Captain, HCMUTE
- **Tran Duc Anh** – AWS Cloud Club Captain, SGU
- **Tran Doan Cong Ly** – AWS Cloud Club Captain, PTIT
- **Danh Hoang Hieu Nghi** – AWS Cloud Club Captain, HUFLIT
- **Huynh Hoang Long** – AWS Community Builder
- **Dinh Le Hoang Anh** – AWS Community Builder
- **Van Hoang Kha** – Cloud Security Engineer, AWS Community Builder
- **Mendel Grabski (Long)** – Ex-Head of Security & DevOps, Cloud Security Solution Architect
- **Tinh Truong** – Platform Engineer, TymeX, AWS Community Builder

---

## Điểm nổi bật Chính

### **1. Sáng kiến AWS Cloud Club**

Sự kiện bắt đầu với phần giới thiệu về AWS Cloud Club, một chương trình được thiết kế để:
- Giúp sinh viên và chuyên gia khám phá và phát triển kỹ năng điện toán đám mây của họ.
- Phát triển khả năng lãnh đạo kỹ thuật và cơ hội cố vấn.
- Xây dựng các kết nối có ý nghĩa trong cộng đồng AWS toàn cầu.

**Lợi ích của việc tham gia AWS Cloud Club:**
- Trải nghiệm AWS thực tế thông qua các hội thảo và dự án.
- Cố vấn từ các chuyên gia AWS.
- Hỗ trợ sự nghiệp lâu dài và cơ hội kết nối mạng.

Các AWS Cloud Club tham gia:
- HCMUTE
- SGU
- PTIT
- HUFLIT

---

### **2. Quản lý Danh tính & Truy cập (IAM)**

IAM là một dịch vụ AWS nền tảng để quản lý quyền truy cập an toàn vào các tài nguyên AWS. Phiên họp bao gồm:
- **Các khái niệm Cốt lõi:**
  - Users (Người dùng), Groups (Nhóm), Roles (Vai trò), và Policies (Chính sách).
  - Xác thực (Authentication) và Ủy quyền (Authorization).
- **Thực tiễn Tốt nhất:**
  - Áp dụng **Nguyên tắc Đặc quyền Tối thiểu**.
  - Xóa các khóa truy cập root sau khi tạo tài khoản.
  - Tránh sử dụng ký tự đại diện (`*`) trong các chính sách.
  - Sử dụng AWS Single Sign-On (SSO) để quản lý truy cập tập trung.

**Các tính năng IAM Nâng cao:**
- **Service Control Policies (SCPs):** Các chính sách toàn tổ chức xác định các quyền tối đa có sẵn cho các tài khoản.
- **Permission Boundaries:** Giới hạn các quyền tối đa mà một người dùng hoặc vai trò có thể có.
- **Xác thực Đa yếu tố (MFA):**
  - **TOTP (Time-based One-Time Password):** Yêu cầu nhập thủ công mã 6 chữ số.
  - **FIDO2 (Fast Identity Online):** Sử dụng quét sinh trắc học hoặc token phần cứng để xác thực.

**Xoay vòng Thông tin xác thực với AWS Secrets Manager:**
- Tự động hóa việc xoay vòng thông tin xác thực bằng quy trình 4 bước: Tạo, Đặt, Kiểm tra, và Hoàn tất Bí mật.
- Tích hợp với EventBridge để lập lịch và tự động hóa.

---

### **3. Phát hiện & Giám sát Liên tục**

Phiên họp này nhấn mạnh tầm quan trọng của khả năng hiển thị thời gian thực và phát hiện mối đe dọa chủ động:
- **Khả năng hiển thị Bảo mật Đa lớp:**
  - **Sự kiện Quản lý:** Các cuộc gọi API và hành động trên bảng điều khiển.
  - **Sự kiện Dữ liệu:** Truy cập đối tượng S3 và thực thi Lambda.
  - **Sự kiện Hoạt động Mạng:** VPC Flow Logs để giám sát cấp mạng.
- **Kiến trúc Hướng Sự kiện với EventBridge:**
  - Xử lý sự kiện thời gian thực để cảnh báo và phản ứng tự động.
  - Tích hợp với Lambda, SNS, và SQS cho các quy trình làm việc bảo mật.
- **Detection-as-Code:**
  - Sử dụng các truy vấn CloudTrail Lake để săn tìm mối đe dọa nâng cao.
  - Các quy tắc phát hiện được kiểm soát phiên bản quản lý trong kho lưu trữ mã.

---

### **4. GuardDuty – Phát hiện Mối đe dọa Thông minh**

GuardDuty cung cấp khả năng phát hiện mối đe dọa liên tục sử dụng ba nguồn dữ liệu chính:
| **Nguồn Dữ liệu**       | **Cái nó Giám sát**                  | **Ví dụ**                                   |
|-----------------------|---------------------------------------|-----------------------------------------------|
| **CloudTrail Events** | Hành động IAM, thay đổi quyền      | Tắt ghi nhật ký để che giấu dấu vết.           |
| **VPC Flow Logs**     | Lưu lượng mạng                      | EC2 gửi dữ liệu đến máy chủ C2 botnet.      |
| **DNS Logs**          | Truy vấn DNS                         | Phần mềm độc hại truy vấn các miền đào tiền ảo.       |

**Các gói Bảo vệ Nâng cao:**
- **S3 Protection:** Phát hiện các mẫu truy cập bất thường và quét phần mềm độc hại.
- **EKS Protection:** Giám sát nhật ký kiểm toán Kubernetes để tìm truy cập trái phép.
- **Malware Protection:** Quét các volume EBS để tìm các instance bị xâm nhập.
- **RDS Protection:** Phát hiện các cuộc tấn công brute-force vào cơ sở dữ liệu.
- **Lambda Protection:** Giám sát lưu lượng mạng từ các hàm Lambda.

---

### **5. Bảo vệ Cơ sở hạ tầng**

Phiên họp bao gồm các kiểm soát bảo mật mạng chính:
- **Security Groups (SG):** Tường lửa trạng thái (stateful) ở cấp độ instance.
- **Network ACLs (NACLs):** Tường lửa không trạng thái (stateless) ở cấp độ subnet.
- **AWS Network Firewall:** Cung cấp ngăn chặn xâm nhập và lọc đầu ra.

---

### **6. Bảo vệ Dữ liệu & Quản trị**

Phiên họp nêu bật các dịch vụ AWS để bảo mật dữ liệu:
- **Mã hóa với KMS:** Bảo vệ dữ liệu bằng các khóa do khách hàng quản lý.
- **AWS Secrets Manager:** Tự động hóa xoay vòng thông tin xác thực.
- **Quản lý Chứng chỉ với ACM:** Cung cấp chứng chỉ công khai miễn phí với khả năng tự động gia hạn.

---

### **7. Ứng phó Sự cố**

Phiên cuối cùng tập trung vào việc chuẩn bị và ứng phó với các sự cố bảo mật:
- **Thực tiễn Tốt nhất:**
  - Sử dụng thông tin xác thực tạm thời.
  - Tránh để lộ các bucket S3 trực tiếp.
  - Quản lý cơ sở hạ tầng thông qua IaC.
- **Quy trình Ứng phó Sự cố:**
  1. Chuẩn bị
  2. Phát hiện & Phân tích
  3. Ngăn chặn
  4. Loại bỏ & Phục hồi
  5. Đánh giá sau Sự cố

---

## Trải nghiệm Sự kiện

Hội thảo này rất phù hợp với dự án của chúng tôi về **Tự động Ứng phó Sự cố và Điều tra Số**. Những bài học chính bao gồm:
- **Độ trễ của GuardDuty:** Các phát hiện mất tới 5 phút do phân tích tập dữ liệu lớn. Các công cụ bên thứ ba như Open Clarity có thể cung cấp các phát hiện gần thời gian thực.
- **Hỗ trợ từ Chuyên gia:** Mendel Grabski đã cung cấp những thông tin giá trị và bày tỏ sự quan tâm đến việc hỗ trợ dự án của chúng tôi.

---

## Hình ảnh Sự kiện

- ![Ảnh nhóm với các diễn giả](/images/4-EventParticipated/4.4-Event4/PicturewithSpeakers.jpg)
  _Ảnh nhóm với Mendel Grabski và Van Hoang Kha._
