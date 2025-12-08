---
title: "Sự kiện 1"
date: "2025-09-18"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Báo cáo Tóm tắt: “Vòng đời Phát triển Định hướng AI: Tái định hình Kỹ thuật Phần mềm”

### Mục tiêu Sự kiện

Sự kiện nhằm cung cấp sự hiểu biết sâu sắc về tác động chuyển đổi của AI tạo sinh đối với phát triển phần mềm. Các mục tiêu chính bao gồm:

- Giới thiệu khung Vòng đời Phát triển Định hướng AI (AI-DLC) và các nguyên tắc nền tảng của nó.
- Trình diễn khả năng của Kiro và Amazon Q Developer như các công cụ hỗ trợ phát triển định hướng AI.
- Khám phá cách AI tạo sinh có thể nâng cao năng suất và hợp lý hóa quy trình kỹ thuật phần mềm.

### Diễn giả

Phiên họp có sự chia sẻ từ hai diễn giả nổi bật:

- **Toan Huynh** – Specialist SA, PACE
- **My Nguyen** – Senior Prototyping Architect, Amazon Web Services - ASEAN

### Điểm nổi bật Chính

Sự kiện tập trung vào khung AI-DLC, tái định hình phát triển phần mềm bằng cách định vị AI là đối tác cộng tác. Các khái niệm chính bao gồm:

- **Khái niệm Cốt lõi AI-DLC:** Khung nhấn mạnh cách tiếp cận lấy con người làm trung tâm, trong đó AI đóng vai trò là cộng tác viên để tăng cường khả năng của lập trình viên. Điều này dẫn đến chu kỳ phát triển được tăng tốc, giảm thời gian từ vài tuần hoặc vài tháng xuống chỉ còn vài giờ hoặc vài ngày.

- **Quy trình làm việc AI-DLC:** Quy trình lặp lại luân phiên giữa các nhiệm vụ do AI điều khiển (ví dụ: tạo kế hoạch, triển khai giải pháp, tìm kiếm sự làm rõ) và các nhiệm vụ do con người điều khiển (ví dụ: cung cấp sự làm rõ, xác thực giải pháp). AI chỉ thực thi các giải pháp sau khi con người xác thực, đảm bảo chất lượng và sự liên kết.

- **Các giai đoạn AI-DLC:** Vòng đời được chia thành ba giai đoạn riêng biệt:
  - **Khởi tạo (Inception):** Thiết lập bối cảnh, làm rõ ý định của người dùng thông qua user stories, và lập kế hoạch nhiệm vụ sử dụng Units of Work.
  - **Xây dựng (Construction):** Mô hình hóa miền, tạo mã, kiểm thử và triển khai cơ sở hạ tầng dưới dạng mã (IaC) với các bài kiểm thử tự động.
  - **Vận hành (Operation):** Quản lý triển khai sản xuất và giải quyết sự cố.

- **Các thách thức được giải quyết bởi AI-DLC:**
  - Mở rộng phát triển AI cho các dự án phức tạp.
  - Tăng cường kiểm soát và cộng tác với các tác nhân AI (AI agents).
  - Duy trì chất lượng mã từ giai đoạn proof-of-concept đến sản xuất.

### Đi sâu: Kiro - IDE AI cho Prototype đến Production

Phiên họp bao gồm một bản demo chi tiết về **Kiro**, một Môi trường Phát triển Tích hợp (IDE) ưu tiên AI được thiết kế để hỗ trợ khung AI-DLC. Các tính năng chính của Kiro bao gồm:

- **Phát triển dựa trên Đặc tả (Spec-Driven Development):** Kiro chuyển đổi các lời nhắc cấp cao (ví dụ: "Xây dựng ứng dụng trò chuyện giống Slack") thành các tạo tác có cấu trúc như:
  - `requirements.md` cho các yêu cầu rõ ràng.
  - `design.md` cho thiết kế hệ thống.
  - `tasks.md` cho các nhiệm vụ rời rạc, có thể hành động.
  Cách tiếp cận có cấu trúc này đảm bảo khả năng truy xuất nguồn gốc và chuyển việc phát triển từ viết mã dựa trên trực giác sang một quy trình có hệ thống.

- **Quy trình làm việc Agentic:** Các tác nhân AI của Kiro tự chủ thực hiện các nhiệm vụ trong khi vẫn giữ quyền kiểm soát cho lập trình viên. Các tính năng chính bao gồm:
  - **Kế hoạch Triển khai:** Kiro tạo ra các kế hoạch chi tiết với các nhiệm vụ và nhiệm vụ phụ liên kết với các yêu cầu cụ thể để xác thực.
  - **Agent Hooks:** Các hook này kích hoạt các tác nhân AI thực hiện các nhiệm vụ như tạo tài liệu, viết kiểm thử đơn vị, hoặc tối ưu hóa hiệu suất mã trong nền.

### Bài học Chính

- **Sẵn sàng cho Sản xuất Định hướng AI:** Kiro đảm bảo mã sẵn sàng cho sản xuất bằng cách tạo các tài liệu thiết kế chi tiết (ví dụ: sơ đồ luồng dữ liệu, hợp đồng API) và kiểm thử đơn vị trước khi bắt đầu triển khai.
- **Kiểm soát của Con người thông qua Tạo tác:** Lập trình viên duy trì sự giám sát bằng cách xác thực và tinh chỉnh các tạo tác (yêu cầu, thiết kế, kế hoạch nhiệm vụ) trước khi các tác nhân AI thực thi việc triển khai.

### Áp dụng Kiến thức vào Công việc

Sự kiện đã cung cấp những hiểu biết có thể hành động để tích hợp các công cụ định hướng AI vào quy trình làm việc của tôi:

- **Áp dụng Trợ lý Viết mã AI:** Các công cụ như Amazon Q Developer có thể tự động hóa các nhiệm vụ lặp đi lặp lại, cho phép tôi tập trung vào các hoạt động có giá trị cao.
- **Ưu tiên Nhiệm vụ Lấy con người làm trung tâm:** Bằng cách giao các nhiệm vụ thường ngày cho AI, tôi có thể dành nhiều thời gian hơn cho các hoạt động sáng tạo và chiến lược như mô hình hóa miền và thiết kế kiến trúc.

### Trải nghiệm Sự kiện

Tham dự sự kiện **AI-Driven Development Life Cycle: Reimagining Software Engineering** là một trải nghiệm mở mang tầm mắt. Phiên họp đã làm nổi bật cách AI tạo sinh đang phát triển từ một trợ lý viết mã thành một người điều phối trung tâm của quy trình phát triển. Cách tiếp cận có cấu trúc của AI-DLC, kết hợp với các công cụ như Kiro, đã chứng minh tiềm năng cách mạng hóa kỹ thuật phần mềm.

Bản demo trực tiếp của Kiro đặc biệt ấn tượng, cho thấy một lời nhắc văn bản đơn giản có thể được chuyển đổi thành một kế hoạch phát triển toàn diện, có thể thực thi như thế nào. Cách tiếp cận này không chỉ tăng tốc độ phát triển mà còn đảm bảo khả năng truy xuất và bảo trì.

### Bài học Rút ra

- Cách tiếp cận có cấu trúc, được con người xác thực của AI-DLC giải quyết các thách thức quan trọng trong phát triển định hướng AI, bao gồm khả năng mở rộng, kiểm soát và chất lượng mã.
- AI tạo sinh, khi được tích hợp một cách thấu đáo, có thể nâng cao đáng kể năng suất trong khi vẫn duy trì các tiêu chuẩn chất lượng cao.

### Hình ảnh Sự kiện

![Hình ảnh nhóm trong sự kiện](/images/4-EventParticipated/4.1-Event1/TheBois-AIDLC.jpg)
