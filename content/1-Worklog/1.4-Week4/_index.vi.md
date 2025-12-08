---
title: "Nhật ký Tuần 4"
date: "2025-09-29"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu Tuần 4:
*   Xây dựng CloudWatch Dashboard tùy chỉnh để trực quan hóa nhật ký và số liệu.
*   Triển khai tự động hóa tối ưu hóa chi phí sử dụng Lambda và EventBridge.
*   Thực hiện di chuyển cơ sở dữ liệu không đồng nhất (MSSQL sang MySQL) sử dụng AWS SCT.
*   Hoàn thiện đề xuất dự án nhóm và ước tính chi phí tài nguyên.

### Các nhiệm vụ thực hiện trong tuần:
| Ngày | Nhiệm vụ                                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |**Xây dựng bảng điều khiển CloudWatch để trực quan hóa các số liệu chính và cảnh báo từ workshop AWS CloudWatch.**<br>&emsp;+ Mở **CloudWatch console**, điều hướng đến **Dashboards**, và tạo một **bảng điều khiển tùy chỉnh** mới với tên mô tả.<br>&emsp;+ Thêm **các tiện ích số liệu** hiển thị **số liệu đếm lỗi** tùy chỉnh được tạo từ **bộ lọc số liệu CloudWatch Logs**, điều chỉnh khoảng thời gian và thống kê để dễ đọc.<br>&emsp;+ Đặt **các tiện ích cảnh báo** trên bảng điều khiển để hiển thị trạng thái thời gian thực của **cảnh báo bắt nguồn từ nhật ký**, liên kết nhật ký, số liệu, và cảnh báo trong một chế độ xem.<br>&emsp;+ Sắp xếp và thay đổi kích thước các tiện ích trên lưới 24 ô để làm nổi bật các thành phần quan sát quan trọng và lưu bảng điều khiển để tái sử dụng.  | 29/09/2025 | 29/09/2025 | [AWS CloudWatch Workshop :: AWS Account Setup](https://000008.awsstudygroup.com/)<br><br>[CloudWatch Dashboards :: AWS Account Setup](https://000008.awsstudygroup.com/6-cloud-watch-dashboard/)<br><br>[Using Amazon CloudWatch dashboards - AWS Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html)<br><br>[Creating a customized CloudWatch dashboard - AWS Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_dashboard.html) |
| 3 | - Hoàn thành **Being a researcher (in Information Science and Technology)** trên Coursera **(ENW493c)** | 30/09/2025 | 30/09/2025 | |
| 4   |- Hoàn thành **Advanced Writing** trên Coursera **(ENW493c)**| 01/10/2025 | 01/10/2025 <br>| |
| 5   |**Tự động hóa tối ưu hóa chi phí EC2 sử dụng các hàm Lambda, thẻ (tags), và thông báo Slack để kiểm soát khởi động/dừng.**<br>&emsp;+ Tạo một **VPC**, **subnets**, và **security group** riêng để host một **EC2 instance** phòng lab mục tiêu cho việc lập lịch tự động.<br>&emsp;+ Khởi chạy và gắn thẻ một **EC2 instance** với thẻ tối ưu hóa chi phí (ví dụ, **environment_auto**) để chỉ các instance cụ thể bị ảnh hưởng bởi tự động hóa.<br>&emsp;+ Cấu hình một **Slack Incoming Webhook** và kênh để nhận thông báo thời gian thực từ **AWS Lambda** về các hành động khởi động/dừng EC2.<br>&emsp;+ Tạo một **IAM execution role** cho **Lambda** với quyền mô tả, khởi động, và dừng các EC2 instance được gắn thẻ và ghi log.<br>&emsp;+ Triển khai hai **hàm Lambda** (start/stop) lọc các EC2 instance theo thẻ, gọi các API **StartInstances**/**StopInstances**, và đăng các tin nhắn có cấu trúc lên Slack.[10]<br>&emsp;+ Kiểm tra quy trình đầu cuối bằng cách gọi các hàm, xác thực thay đổi trạng thái EC2 trong bảng điều khiển, và xác nhận thông báo Slack làm cơ sở cho giải pháp được lập lịch sử dụng **EventBridge/CloudWatch Events**.<br>- **Thảo luận với nhóm** về những việc cần làm với **dự án** của chúng tôi và cách chúng tôi có thể triển khai **Slack**| 02/10/2025 | 02/10/2025 | [Optimize EC2 cost with Lambda - AWS Study Group](https://000022.awsstudygroup.com)<br><br>[Defining Lambda function permissions with an execution role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html)<br><br>[How to Schedule EC2 Instances to Stop/Start Automatically](https://dev.to/aws-builders/how-to-schedule-ec2-instances-to-stopstart-automatically-1bl5)<br><br>[Use AWS Lambda to send Slack notifications for running Amazon EC2 instances](https://nivleshc.wordpress.com/2021/06/27/use-aws-lambda-to-send-slack-notifications-for-running-amazon-ec2-instances) |
| 6   |- Tham gia sự kiện **AI-Driven Development Life Cycle: Reimagining Software Engineering**| 03/10/2025 | 04/10/2025 |  | 


### Kết quả đạt được Tuần 4:
*   Đã thiết kế và triển khai CloudWatch Dashboard tùy chỉnh để giám sát sức khỏe ứng dụng và tỷ lệ lỗi.
*   Phát triển giải pháp tối ưu hóa chi phí serverless sử dụng Lambda để tự động dừng/chạy các EC2 instance, tích hợp với thông báo Slack.
*   Di chuyển thành công cơ sở dữ liệu MSSQL cũ sang Amazon MySQL sử dụng AWS Schema Conversion Tool (SCT), giải quyết các vấn đề tương thích.
*   Phối hợp với nhóm để hoàn thiện đề xuất dự án đồ án và đảm bảo quyền truy cập quản trị cho tất cả các thành viên.
