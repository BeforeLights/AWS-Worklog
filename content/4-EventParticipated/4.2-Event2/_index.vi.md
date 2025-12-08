---
title: "Sự kiện 2"
date: "2025-11-15"
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Báo cáo Tóm tắt: “AWS Cloud Mastery Series #1 - AI/ML/GenAI trên AWS”

### Mục tiêu Sự kiện

Sự kiện nhằm cung cấp một cái nhìn tổng quan về khả năng của AI, Machine Learning (ML) và Generative AI (GenAI) trên AWS. Các mục tiêu cụ thể bao gồm:

- Khám phá các khái niệm nền tảng của Generative AI và các ứng dụng của nó.
- Trình diễn việc sử dụng các dịch vụ và công cụ AWS cho quy trình làm việc AI/ML.
- Nêu bật các phương pháp hay nhất (best practices) để tích hợp AI/ML vào môi trường sản xuất.

### Diễn giả

Sự kiện có sự tham gia của một nhóm đa dạng các chuyên gia giàu kinh nghiệm đã chia sẻ kiến thức chuyên môn của họ:

- **Lam Tuan Kiet** – Senior DevOps Engineer, FPT Software
- **Danh Hoang Hieu Nghi** – AI Engineer, Renova Cloud
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey
- **Van Hoang Kha** – Cloud Security Engineer, AWS Community Builder

### Điểm nổi bật Chính

#### Generative AI với Amazon Bedrock

Phiên họp đã cung cấp một sự khám phá sâu về Amazon Bedrock, một dịch vụ được quản lý hoàn toàn để triển khai và mở rộng các mô hình nền tảng (foundation models). Các chủ đề chính bao gồm:

- **Foundation Models:** Khác với các mô hình truyền thống, các mô hình nền tảng được đào tạo trước trên các tập dữ liệu khổng lồ và có thể được điều chỉnh cho một loạt các nhiệm vụ. Amazon Bedrock cung cấp các mô hình từ các công ty AI hàng đầu như OpenAI, Anthropic, và Cohere.

- **Prompt Engineering:** Các kỹ thuật để tạo ra các lời nhắc hiệu quả nhằm tối ưu hóa phản hồi của mô hình:
  - **Zero-Shot Prompting:** Không cung cấp bối cảnh hoặc ví dụ trước.
  - **Few-Shot Prompting:** Bao gồm một vài ví dụ để hướng dẫn mô hình.
  - **Chain of Thought (CoT):** Kết hợp các bước suy luận để cải thiện chất lượng phản hồi.

- **Retrieval Augmented Generation (RAG):** Một kỹ thuật nâng cao phản hồi của mô hình bằng cách truy xuất thông tin liên quan từ các nguồn dữ liệu bên ngoài:
  - **Retrieval (Truy xuất):** Lấy dữ liệu liên quan từ cơ sở tri thức.
  - **Augmentation (Tăng cường):** Thêm dữ liệu đã truy xuất làm bối cảnh cho lời nhắc.
  - **Generation (Tạo sinh):** Tạo phản hồi dựa trên lời nhắc đã được tăng cường.
  - **Các trường hợp sử dụng:** Chatbot theo ngữ cảnh, tìm kiếm cá nhân hóa, tóm tắt dữ liệu thời gian thực, và cải thiện việc tạo nội dung.

- **Amazon Titan Embedding:** Một mô hình nhẹ được thiết kế cho các nhiệm vụ truy xuất độ chính xác cao. Nó dịch văn bản thành các embedding số và hỗ trợ hơn 100 ngôn ngữ, làm cho nó trở nên lý tưởng cho các ứng dụng đa ngôn ngữ.

#### Các dịch vụ AI được đào tạo trước trên AWS

AWS cung cấp một bộ các dịch vụ AI sẵn sàng sử dụng để giải quyết các nhu cầu kinh doanh phổ biến:
- **Amazon Rekognition:** Phân tích hình ảnh và video.
- **Amazon Translate:** Phát hiện và dịch văn bản.
- **Amazon Textract:** Trích xuất văn bản và bố cục từ tài liệu.
- **Amazon Transcribe:** Chuyển đổi giọng nói thành văn bản.
- **Amazon Polly:** Tổng hợp văn bản thành giọng nói.
- **Amazon Comprehend:** Phân tích văn bản để tìm thông tin chi tiết và mối quan hệ.
- **Amazon Kendra:** Khả năng tìm kiếm thông minh.
- **Amazon Lookout:** Phát hiện bất thường trong các chỉ số, thiết bị và hình ảnh.
- **Amazon Personalize:** Đề xuất cá nhân hóa cho người dùng.

#### Amazon Bedrock AgentCore

Phiên họp đã giới thiệu **Amazon Bedrock AgentCore**, một nền tảng để triển khai và mở rộng quy mô các tác nhân AI một cách an toàn trong sản xuất. Các tính năng chính bao gồm:
- **Bộ nhớ:** Cho phép các tác nhân ghi nhớ các tương tác trong quá khứ và học hỏi theo thời gian.
- **Kiểm soát Danh tính và Truy cập:** Đảm bảo thực thi an toàn các quy trình tác nhân.
- **Tích hợp Công cụ:** Hỗ trợ các công cụ như trình duyệt và trình thông dịch mã cho các quy trình làm việc phức tạp.
- **Khả năng quan sát:** Cung cấp thông tin chi tiết về các tương tác của tác nhân để kiểm toán và gỡ lỗi.
- **Khung xây dựng Tác nhân:** Bao gồm CrewAI, LangChain, OpenAI Agents SDK, và nhiều hơn nữa.

#### Demo Trực tiếp: AMZPhoto
Bản demo đã giới thiệu một ứng dụng nhận dạng khuôn mặt được xây dựng bằng các dịch vụ AI của AWS. Ứng dụng đã chứng minh sự tích hợp liền mạch của Amazon Rekognition để phân tích hình ảnh.

### Bài học Chính

- **Amazon Bedrock như một Trung tâm GenAI:** Bedrock đơn giản hóa việc truy cập vào các mô hình nền tảng từ các nhà cung cấp hàng đầu, cho phép phát triển nhanh chóng các giải pháp AI.
- **Prompt Engineering và RAG:** Các kỹ thuật nhắc nhở hiệu quả và tạo sinh tăng cường truy xuất có thể nâng cao đáng kể hiệu suất mô hình.
- **Titan Embeddings cho Tìm kiếm:** Amazon Titan Embedding là một công cụ mạnh mẽ để truy xuất thông tin với độ chính xác cao.
- **Dịch vụ AI được đào tạo trước:** AWS cung cấp một loạt các dịch vụ để giải quyết các nhu cầu AI/ML đa dạng, từ phân tích hình ảnh đến đề xuất cá nhân hóa.
- **AgentCore cho AI Sẵn sàng Sản xuất:** Bedrock AgentCore giải quyết các thách thức trong việc triển khai các tác nhân AI ở quy mô lớn, đảm bảo bảo mật, khả năng mở rộng và khả năng quan sát.

### Áp dụng Kiến thức vào Công việc

Kiến thức thu được từ sự kiện này có thể được áp dụng theo một số cách:
- **Tích hợp Mô hình Nền tảng:** Kết hợp các mô hình nền tảng vào các dự án trong tương lai để nâng cao khả năng AI.
- **Tối ưu hóa Quy trình làm việc với RAG:** Sử dụng tạo sinh tăng cường truy xuất để cải thiện chất lượng của các giải pháp định hướng AI.
- **Tận dụng Dịch vụ Đào tạo trước:** Sử dụng các dịch vụ AI của AWS như Rekognition và Textract để tự động hóa các nhiệm vụ lặp lại và cải thiện hiệu quả.
- **Xây dựng Tác nhân AI có thể mở rộng:** Khám phá Bedrock AgentCore để triển khai các tác nhân AI an toàn và có thể mở rộng trong môi trường sản xuất.

### Trải nghiệm Sự kiện

Sự kiện rất hấp dẫn và nhiều thông tin, với các diễn giả chuẩn bị kỹ lưỡng và các phiên tương tác. Những điểm nổi bật chính của trải nghiệm bao gồm:
- **Phiên Hỏi & Đáp:** Một thành viên trong nhóm đã nêu một câu hỏi quan trọng về việc xử lý khối lượng cảnh báo lớn trong kiến trúc sử dụng SNS cho các phát hiện của GuardDuty. Giải pháp được đưa ra là tích hợp SQS để xếp hàng các sự kiện, đảm bảo không bỏ sót cảnh báo nào.
- **Kahoot Quiz:** Đã lọt vào top 3 cho đến khi Ragnarok bắt đầu...
- **Kết nối (Networking):** Đã thành lập một nhóm không chính thức, "Mèo Cam Đeo Khăn," hợp tác với các người tham dự khác, thúc đẩy kết nối và cơ hội hợp tác trong tương lai.

### Hình ảnh Sự kiện
- ![Nhóm Mèo Cam Đeo Khăn](/images/4-EventParticipated/4.2-Event2/Meocamdeokhan.jpg)
