---
title: "Nhật ký Tuần 5"
date: "2025-10-06"
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu Tuần 5:
*   Thiết lập môi trường DNS lai (Hybrid DNS) sử dụng Route 53 Resolver Endpoints (Inbound/Outbound).
*   Tích hợp AWS Managed Microsoft AD với các mô phỏng on-premises thông qua RD Gateway.
*   Thành thạo việc giảm thiểu các thao tác thủ công bằng cách thực hiện các tác vụ cốt lõi qua AWS CLI.
*   Dịch các bài blog kỹ thuật để làm sâu sắc thêm hiểu biết về các khái niệm đám mây.

### Các nhiệm vụ thực hiện trong tuần:
| Ngày | Nhiệm vụ                                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   |**Hoàn thành thiết lập đầu cuối môi trường DNS lai sử dụng Route 53 Resolver với AWS Managed Microsoft AD và RD Gateway.**<br>&emsp;+ Khởi chạy mẫu **CloudFormation** được cung cấp để tạo một **VPC** tùy chỉnh, các subnet công khai/riêng tư trên hai **Availability Zones**, **Internet Gateway**, và **NAT Gateways** để truy cập ra ngoài từ các subnet riêng tư.<br>&emsp;+ Cấu hình một **Remote Desktop Gateway (RDGW) EC2 instance** trong subnet công khai, điều chỉnh **security groups** để kiểm soát truy cập **RDP/ICMP**, và xác minh kết nối từ xa từ máy trạm cục bộ.<br>&emsp;+ Triển khai **AWS Managed Microsoft AD**, gia nhập RDGW vào miền được quản lý, và xác nhận xác thực miền từ máy chủ phiên RD. <br>&emsp;+ Tạo **Route 53 Resolver outbound endpoints** trong các subnet riêng tư và các quy tắc chuyển tiếp để khối lượng công việc VPC có thể phân giải tên miền kiểu on-premises thông qua các máy chủ DNS AD được quản lý. <br>&emsp;+ Tạo **Route 53 Resolver inbound endpoints** và các quy tắc để cho phép các trình chuyển tiếp DNS bên ngoài hoặc on-premises phân giải tên máy chủ AWS riêng tư trong VPC, hoàn thành luồng DNS lai. <br>&emsp;+ Kiểm tra phân giải tên DNS từ RDGW instance để đảm bảo các truy vấn cho cả **bản ghi riêng tư AWS và miền kiểu on-premises** được định tuyến chính xác qua các Resolver endpoints và AD DNS đã cấu hình. | 06/10/2025 | 06/10/2025      | [AWS Managed Microsoft AD - AWS Directory Service](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/directory_microsoft_ad.html)<br><br>[What is Route 53 VPC Resolver?](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resolver.html)<br><br>[NAT Gateways - Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| 3   |Dịch **Blog 1** và **Blog 2** | 07/10/2025 | 07/10/2025 | [**Blog 1**](3-BlogsTranslated/3.1-Blog1/_index.md)<br><br>[**Blog 2**](3-BlogsTranslated/3.2-Blog2/_index.md) |
| 4   | **Hoàn thành thực hành AWS CLI đầu cuối trên các dịch vụ cốt lõi (S3, SNS, IAM, VPC, EC2) sử dụng hồ sơ xác thực SSO.**<br>&emsp;+ Sử dụng **AWS CLI với Amazon S3** để tạo và kiểm tra các S3 bucket và đối tượng thay vì thực hiện các hành động đó trong console.<br>&emsp;+ Thực hành **AWS CLI với Amazon SNS** bằng cách tạo chủ đề (topics), thêm đăng ký email, và gửi thông báo thử nghiệm.<br>&emsp;+ Quản lý **các định danh IAM qua AWS CLI**, tạo người dùng/nhóm và xử lý các khóa truy cập thông qua dòng lệnh.<br>&emsp;+ Xây dựng mạng với **VPC và Internet Gateway sử dụng AWS CLI**, tạo một VPC tùy chỉnh, subnets, và định tuyến công khai để truy cập internet.<br>&emsp;+ Khởi chạy và quản lý một **EC2 instance qua AWS CLI**, kiểm tra kết nối SSH, và chấm dứt instance sau khi thực hành.<br>&emsp;+ Chạy tất cả các bài lab sử dụng **`aws login`** thay vì các khóa truy cập tĩnh từ `aws configure`. | 08/10/2025 | 08/10/2025 | [Getting Started with the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)<br><br>[Getting started with Amazon S3 using the AWS CLI](https://docs.aws.amazon.com/AmazonS3/latest/userguide/GettingStartedS3CLI.html)<br><br>[Accessing Amazon SNS in the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-services-sns.html)<br><br>[IAM examples using AWS CLI](https://docs.aws.amazon.com/cli/v1/userguide/cli_iam_code_examples.html)<br><br>[Getting started with Amazon VPC using the AWS CLI](https://docs.aws.amazon.com/vpc/latest/userguide/getting-started-with-amazon-vpc-using-the-aws-cli.html)<br><br>[Using Amazon EC2 in the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2.html)<br><br>[Configuring IAM Identity Center authentication with the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-sso.html) |
| 5   | Dịch **Blog 3** | 09/10/2025 | 09/10/2025 | [**Blog 3**](3-BlogsTranslated/3.3-Blog3/_index.md) |
| 6   | - Hoàn thành **Introduction to Research for Essay Writing** trên Coursera **(ENW493c)** | 10/10/2025 | 10/10/2025 | |

### Kết quả đạt được Tuần 5:
*   Triển khai thành công kiến trúc DNS Lai cho phép phân giải liền mạch giữa on-premises và AWS (Route 53 Resolver).
*   Có kinh nghiệm thực tế với việc tích hợp AWS Managed Microsoft AD và Remote Desktop Gateway.
*   Chứng minh sự thành thạo hoàn toàn trong việc quản lý tài nguyên AWS cốt lõi (VPC, EC2, S3, IAM) chỉ thông qua CLI.
*   Nâng cao kỹ năng giao tiếp kỹ thuật thông qua việc dịch ba bài blog chuyên sâu về kỹ thuật đám mây.
