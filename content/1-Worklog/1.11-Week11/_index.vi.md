---
title: "Nhật ký Tuần 11"
date: "2025-09-09"
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu Tuần 11:
*   Tái cấu trúc các hàm Lambda Cảnh báo thành dịch vụ "Gửi Cảnh báo" (Alert Dispatch) thống nhất, mô-đun.
*   Tích hợp khả năng webhook của Slack để mở rộng các kênh thông báo cảnh báo.
*   Tập trung quản lý thông tin xác thực sử dụng Biến Môi trường Lambda.
*   Tiếp tục hoàn thiện kế hoạch dự án Hệ thống Ứng phó Sự cố trong Jira.

### Các nhiệm vụ thực hiện trong tuần:
| Ngày | Nhiệm vụ                                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |Tham dự sự kiện AWS Cloud Mastery Series #2 – DevOps on AWS| 17/11/2025 | 17/11/2025 ||
| 3   | **Hợp nhất Telegram và SES Lambdas thành một hàm Gửi Cảnh báo (Alert Dispatch) thống nhất với mã có cấu trúc, tích hợp triển khai Slack của bạn bè, và xác thực mọi thứ với GuardDuty.**<br>&emsp;+ Hợp nhất **các hàm Telegram và SES Lambda riêng biệt** thành một **Alert Dispatch Lambda** duy nhất với cấu trúc mã sạch, mô-đun và các hàm trợ giúp chuyên dụng cho từng kênh.<br>&emsp;+ Tích hợp **gửi Slack webhook** từ mã của bạn tôi—bây giờ cả ba kênh (Telegram, SES, Slack) đều được xử lý bởi một hàm với logic phân tích được chia sẻ.<br>&emsp;+ Cấu trúc **mã Lambda đúng cách** với sự phân tách rõ ràng: phân tích SNS → làm giàu cảnh báo → bộ định dạng cụ thể cho kênh (Slack blocks, tin nhắn Telegram, SES HTML) → xử lý lỗi.<br>&emsp;+ Thiết lập **biến môi trường** để quản lý tập trung tất cả thông tin xác thực (URL webhook Slack, token bot/ID trò chuyện/ID luồng Telegram, địa chỉ người gửi SES)—sạch sẽ hơn nhiều so với mã hóa cứng.<br>&emsp;+ Kiểm tra **đường ống đa kênh hoàn chỉnh** với các phát hiện mẫu GuardDuty—xác minh cảnh báo đến được định dạng chính xác trong Slack, Telegram, và email cùng lúc, và mọi thứ hoạt động đáng tin cậy.| 18/11/2025 | 18/11/2025 ||
| 4   |**Cấu trúc dự án Hệ thống Ứng phó Sự cố AWS trong Jira bằng cách xác định các epic cốt lõi, gán quyền sở hữu trên nhiều nhóm, và thiết lập nền tảng cho các quy trình xử lý sự cố.**<br>&emsp;+ Tạo **5 epic chính** trong Jira để ánh xạ quy trình ứng phó sự cố: Phát hiện mối đe dọa, Cảnh báo, Quy trình Ứng phó, Đường ống dữ liệu, và Thành phần Bảng điều khiển.<br>&emsp;+ Gán **quyền sở hữu epic cho các thành viên nhóm cá nhân** để mỗi khu vực có một người dẫn đầu rõ ràng chịu trách nhiệm cho phạm vi và việc giao hàng của nó.<br>&emsp;+ Tổ chức **cấu trúc và trách nhiệm nhóm** bằng cách căn chỉnh từng epic với bộ kỹ năng phù hợp (phát hiện mối đe dọa, cơ sở hạ tầng cảnh báo, điều phối quy trình làm việc, nhập dữ liệu, lập bảng điều khiển).<br>&emsp;+ Cấu hình **phân rã epic-thành-tác vụ** trong Jira để các nhiệm vụ phụ và vấn đề được gắn với epic cha của chúng, cho phép khả năng hiển thị nhóm và theo dõi burndown trên toàn hệ thống ứng phó sự cố.| 19/11/2025 | 19/11/2025 ||
| 5   |Về thăm trường cấp 3 **Bùi Thị Xuân** nhân ngày Nhà giáo Việt Nam.| 20/11/2025 | 20/11/2025 ||
| 6   |Tôi được mời dự **lễ tốt nghiệp** của một người bạn ở **Đại học FPT**.| 21/11/2025 | 21/11/2025 ||


### Kết quả đạt được Tuần 11:
*   Cải thiện đáng kể khả năng bảo trì mã bằng cách hợp nhất các hàm Lambda rời rạc thành một "Alert Dispatcher" duy nhất.
*   Mở rộng hệ thống cảnh báo sự cố để hỗ trợ Telegram, Slack, và SES Email cùng một lúc.
*   Triển khai các phương pháp cấu hình bảo mật bằng cách chuyển thông tin xác thực được mã hóa cứng sang Biến Môi trường.
*   Thực thi tính rõ ràng của dự án bằng cách xác định các Epics và phân công trách nhiệm chi tiết trong Jira.
