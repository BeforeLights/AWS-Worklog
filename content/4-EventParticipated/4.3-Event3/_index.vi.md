---
title: "Sự kiện 3"
date: "2025-11-17"
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Báo cáo Tóm tắt: “AWS Cloud Mastery Series #2 - DevOps trên AWS”

### Tổng quan Sự kiện

Phiên thứ hai của chuỗi AWS Cloud Mastery tập trung vào các thực tiễn và công cụ DevOps có sẵn trên AWS. Sự kiện nhằm cung cấp cho người tham dự sự hiểu biết vững chắc về các nguyên tắc DevOps, Cơ sở hạ tầng dưới dạng Mã (IaC), dịch vụ container, và các giải pháp giám sát để xây dựng các hệ thống dựa trên đám mây có khả năng mở rộng, tin cậy và dễ bảo trì.

---

### Mục tiêu Sự kiện

Các mục tiêu chính của sự kiện là:
- Giới thiệu các dịch vụ AWS DevOps, bao gồm các đường ống CI/CD.
- Khám phá các khái niệm và công cụ Cơ sở hạ tầng dưới dạng Mã (IaC) như AWS CloudFormation, AWS CDK, và Terraform.
- Cung cấp thông tin chi tiết về các dịch vụ container trên AWS, bao gồm Amazon ECS, EKS, và App Runner.
- Nêu bật tầm quan trọng của việc giám sát và khả năng quan sát sử dụng các dịch vụ AWS như CloudWatch và AWS X-Ray.

---

### Diễn giả

Sự kiện có sự tham gia của một nhóm các AWS Community Builders và chuyên gia đám mây giàu kinh nghiệm:
- **Truong Quang Tinh** – Platform Engineer, TymeX
- **Bao Huynh** – AWS Community Builder
- **Nguyen Khanh Phuc Thinh** – AWS Community Builder
- **Tran Dai Vi** – AWS Community Builder
- **Huynh Hoang Long** – AWS Community Builder
- **Pham Hoang Quy** – AWS Community Builder
- **Nghiem Le** – AWS Community Builder
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey

---

### Điểm nổi bật Chính

#### **Tư duy DevOps**
Phiên họp bắt đầu với phần giới thiệu về văn hóa DevOps và các nguyên tắc cốt lõi của nó:
- **Hợp tác:** Phá vỡ rào cản giữa đội ngũ phát triển và vận hành.
- **Tự động hóa:** Hợp lý hóa các nhiệm vụ lặp đi lặp lại để cải thiện hiệu quả.
- **Học tập Liên tục:** Khuyến khích thử nghiệm và học hỏi từ thất bại.
- **Đo lường:** Sử dụng các chỉ số để theo dõi tiến độ và tối ưu hóa quy trình.

**Các vai trò chính trong DevOps:**
- Kỹ sư DevOps
- Kỹ sư Cloud
- Kỹ sư Nền tảng (Platform Engineer)
- Kỹ sư Độ tin cậy Trang web (SRE)

**Chỉ số Thành công:**
- Tần suất và tình trạng triển khai
- Sự ổn định và độ tin cậy của hệ thống
- Cải thiện sự linh hoạt và trải nghiệm khách hàng
- Biện minh cho các khoản đầu tư công nghệ

**Thực tiễn Tốt nhất:**
| NÊN (DO)                        | KHÔNG NÊN (DON'T)           |
|---------------------------------|---------------------------|
| Bắt đầu với các nguyên tắc cơ bản | Mắc kẹt trong hướng dẫn (tutorial hell) |
| Học bằng cách xây dựng dự án thực tế | Copy-paste một cách mù quáng        |
| Tài liệu hóa mọi thứ             | So sánh tiến độ của bạn với người khác |
| Làm chủ từng thứ một     | Bỏ cuộc sau thất bại    |
| Nâng cao kỹ năng mềm         |                           |

**- Tích hợp Liên tục:** Các thành viên trong nhóm tích hợp công việc của họ thường xuyên, hướng tới Chuyển giao và Triển khai liên tục

---

#### **Cơ sở hạ tầng dưới dạng Mã (IaC)**

Sự kiện đã cung cấp cái nhìn sâu sắc về Cơ sở hạ tầng dưới dạng Mã (IaC) và lợi ích của nó:
- **Tự động hóa:** Giảm sự can thiệp thủ công và các lỗi tiềm ẩn.
- **Khả năng mở rộng:** Dễ dàng mở rộng cơ sở hạ tầng lên hoặc xuống dựa trên nhu cầu.
- **Khả năng tái tạo:** Đảm bảo môi trường nhất quán từ phát triển đến sản xuất.
- **Hợp tác:** Tăng cường làm việc nhóm giữa phát triển và vận hành.

**AWS CloudFormation:**
Công cụ IaC gốc của AWS, cho phép người dùng định nghĩa và cung cấp cơ sở hạ tầng AWS bằng cách sử dụng định dạng mẫu khai báo (YAML hoặc JSON).
- **Stack:** Một tập hợp các tài nguyên AWS được quản lý như một đơn vị duy nhất.
- **CloudFormation Template:** Một tệp mô tả các tài nguyên cơ sở hạ tầng cần thiết cho một ứng dụng hoặc dịch vụ cụ thể.
- **Drift Detection:** Xác định và sửa chữa sự khác biệt giữa cấu hình thực tế của stack và cấu hình mong đợi của nó.

**AWS Cloud Development Kit (CDK):**
Một khung phát triển phần mềm mã nguồn mở cho phép người dùng định nghĩa cơ sở hạ tầng đám mây bằng ngôn ngữ lập trình tùy chọn.
- **Construct:** Khối xây dựng cơ bản của AWS CDK, đại diện cho một đơn vị triển khai duy nhất.

**AWS Amplify:**
Một nền tảng phát triển để xây dựng các ứng dụng di động và web an toàn, có thể mở rộng.

**Terraform:**
Một công cụ IaC mã nguồn mở cho phép người dùng định nghĩa và cung cấp cơ sở hạ tầng trung tâm dữ liệu bằng ngôn ngữ cấu hình cấp cao.
- **Điểm mạnh:** Hỗ trợ đa đám mây, quản lý trạng thái, và hệ sinh thái mô-đun lớn.

**Tiêu chí chọn Công cụ IaC:**
- Yêu cầu dự án: đám mây đơn vs. đa đám mây
- Ch chuyên môn của nhóm: tập trung vào nhà phát triển hay vận hành
- Hệ sinh thái và hỗ trợ cộng đồng

---

#### **Dịch vụ Container trên AWS**

Sự kiện bao gồm các dịch vụ container khác nhau do AWS cung cấp và cách chúng phù hợp với bối cảnh DevOps:
- **Docker:** Một nền tảng để phát phát triển, vận chuyển và chạy các ứng dụng trong container.
- **Amazon ECR (Elastic Container Registry):** Một registry container Docker được quản lý hoàn toàn giúp dễ dàng lưu trữ, quản lý và triển khai các image container Docker.
- **Amazon ECS (Elastic Container Service):** Một dịch vụ điều phối container được quản lý hoàn toàn hỗ trợ các container Docker.
- **Amazon EKS (Elastic Kubernetes Service):** Một dịch vụ được quản lý giúp đơn giản hóa việc chạy Kubernetes trên AWS mà không cần cài đặt và vận hành control plane hoặc node Kubernetes của riêng bạn.
- **AWS App Runner:** Một dịch vụ giúp dễ dàng triển khai nhanh chóng các ứng dụng web và API được container hóa.

**Điều phối Container với ECS và EKS:**
- **ECS:** Dịch vụ điều phối container gốc của AWS, tích hợp chặt chẽ với các dịch vụ AWS khác.
- **EKS:** Một dịch vụ Kubernetes được quản lý, cung cấp sự linh hoạt và kiểm soát của Kubernetes mà không cần chi phí vận hành.

---

#### **Giám sát & Khả năng quan sát**

Phiên cuối cùng tập trung vào các giải pháp giám sát và khả năng quan sát có sẵn trên AWS:
- **Amazon CloudWatch:** Một dịch vụ giám sát và khả năng quan sát cung cấp dữ liệu và thông tin chi tiết có thể hành động để giám sát các ứng dụng, phản ứng với các thay đổi hiệu suất toàn hệ thống, và tối ưu hóa sử dụng tài nguyên.
- **AWS X-Ray:** Một dịch vụ giúp các nhà phát triển phân tích và gỡ lỗi các ứng dụng phân tán, sản xuất, chẳng hạn như những ứng dụng được xây dựng bằng kiến trúc vi dịch vụ.

**Các tính năng Chính:**
- **CloudWatch Metrics:** Giám sát và thu thập các chỉ số từ tài nguyên AWS và ứng dụng.
- **CloudWatch Alarms:** Tự động phản ứng với các thay đổi trong tài nguyên AWS của bạn.
- **CloudWatch Logs:** Giám sát, lưu trữ và truy cập các tệp nhật ký từ các phiên bản Amazon EC2, AWS CloudTrail và các nguồn khác.
- **X-Ray Tracing:** Phân tích và gỡ lỗi các ứng dụng phân tán, cung cấp thông tin chi tiết về các tắc nghẽn hiệu suất và lỗi.

---

### Trải nghiệm Sự kiện

Sự kiện này rất quan trọng đối với dự án của chúng tôi vì nó giải quyết kế hoạch thêm IaC bằng CDK, thay vì sử dụng ClickOps để dễ bảo trì và tái tạo. Ngoài ra, một số thông tin chi tiết hơn về CloudWatch đã giúp ích rất nhiều cho tính năng giám sát dữ liệu của chúng tôi.

Các diễn giả đã trả lời câu hỏi của nhóm chúng tôi:

- Hỏi: Dự án của chúng tôi cho đến nay hoàn toàn được xây dựng bằng ClickOps, và chúng tôi đang có kế hoạch sử dụng CDK. Có công cụ nào có thể quét và chuyển cơ sở hạ tầng hiện tại của chúng tôi thành CDK hoặc CloudFormation thay vì tái tạo lại cơ sở hạ tầng từ đầu bằng IaC không? 
- Đáp: Rất tiếc là không, chưa có công cụ nào có thể hỗ trợ vấn đề đó, nhóm của bạn sẽ phải xây dựng lại cơ sở hạ tầng từ đầu. Nếu bạn tình cờ tìm thấy một công cụ có thể hỗ trợ, vui lòng chia sẻ với chúng tôi.

- Hỏi: Chúng tôi nhận thấy rằng AWS X-Ray được sử dụng với CloudWatch tương tự như CloudTrail trong phương pháp theo dõi của nó, bạn có thể giải thích thêm về sự khác biệt giữa chúng không?
- Đáp: X-Ray được sử dụng cho CloudWatch và dùng để theo dõi các tài nguyên và dịch vụ mà hệ thống đã tương tác, trong khi CloudTrail thường được sử dụng để theo dõi các hành động của người dùng AWS.

- Hỏi: Dự án của chúng tôi được xây dựng xung quanh GuardDuty Findings, bạn có kinh nghiệm nào về cách kích hoạt Findings một cách đáng tin cậy cho các kịch bản demo không?
- Đáp: Theo kinh nghiệm của tôi, tôi biết rằng Guard Duty Findings có thể được kích hoạt bởi các hoạt động quét cổng nhưng tôi chắc chắn cũng có những cách khác.
- Đáp: Guard Duty có thể được cấu hình để có danh sách mối đe dọa chứa các quy tắc tùy chỉnh để kích hoạt các phát hiện khi có hoạt động liên quan đến các miền hoặc IP độc hại đã định cấu hình.

Sự kiện này cũng là lần đầu tiên một số diễn giả trình bày về một chủ đề:
- Các phần DevOps và IaC được trình bày tốt.
- Phần Giám sát & Khả năng quan sát không tuyệt vời lắm và chúng tôi có thể nhận thấy sự lo lắng của diễn giả nhưng vẫn mang lại giá trị lớn bất kể điều đó.

#### Một số hình ảnh sự kiện
![Ảnh nhóm trong sự kiện được chụp bởi diễn giả Tran Dai Vi](/images/4-EventParticipated/4.3-Event3/CM2GroupPic.jpg)
