---
title: "Blog 1"
date: "2000-01-01"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# **Xây dựng nền tảng phát sóng dữ liệu thị trường sàn giao dịch hiệu suất cao trên AWS**

bởi Abhishek Sarolia và Avanish Yadav vào ngày 24/09/2025 trong [Amazon ElastiCache](https://aws.amazon.com/blogs/networking-and-content-delivery/category/database/amazon-elasticache/), [Amazon RDS](https://aws.amazon.com/blogs/networking-and-content-delivery/category/database/amazon-rds/), [AWS Direct Connect](https://aws.amazon.com/blogs/networking-and-content-delivery/category/networking-content-delivery/aws-direct-connect/), [AWS Transit Gateway](https://aws.amazon.com/blogs/networking-and-content-delivery/category/networking-content-delivery/aws-transit-gateway/), [Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/category/post-types/best-practices/), [Customer Solutions](https://aws.amazon.com/blogs/networking-and-content-delivery/category/post-types/customer-solutions/), [Database](https://aws.amazon.com/blogs/networking-and-content-delivery/category/database/), [Networking & Content Delivery](https://aws.amazon.com/blogs/networking-and-content-delivery/category/networking-content-delivery/), [RDS for PostgreSQL](https://aws.amazon.com/blogs/networking-and-content-delivery/category/database/amazon-rds/rds-for-postgresql/) | [Permalink](https://aws.amazon.com/blogs/networking-and-content-delivery/building-a-high-performance-exchange-market-data-broadcasting-platform-on-aws/)

*Đây là bài đăng hợp tác cùng Abhishek Chawla, Giám đốc Sản phẩm & Công nghệ; Kartik Manimuthu, Giám đốc Kỹ thuật Đám mây; và Digvijay, Giám đốc Kỹ thuật Ứng dụng tại SMC Global Securities Ltd.*

[SMC Global Securities Ltd.](https://www.smctradeonline.com/) (SMC), thành lập năm 1990, là công ty dịch vụ tài chính hàng đầu Ấn Độ cung cấp các dịch vụ giao dịch, tư vấn tài sản và phân phối sản phẩm tài chính cho các nhà đầu tư cá nhân, công ty và khách hàng giàu có.

SMC Global Securities (SMC) đã hợp tác với [Amazon Web Services (AWS)](https://aws.amazon.com/) để hiện đại hóa hạ tầng giao dịch bán lẻ của họ. Là một phần của sáng kiến này, SMC đã xây dựng hệ thống phân phối dữ liệu tài chính vững chắc trên AWS xử lý hiệu quả luồng dữ liệu thị trường thời gian thực từ các sàn giao dịch lớn của Ấn Độ (NSE, BSE, MCX và NCDEX). Nền tảng này sử dụng [công nghệ mạng Multicast](https://en.wikipedia.org/wiki/Multicast) để thu thập và phát sóng dữ liệu giá sàn với hiệu suất và khả năng mở rộng cao.

Nhiều khách hàng AWS vận hành hệ thống tài chính lõi trên đám mây thường xử lý dữ liệu unicast từ hạ tầng on-premises. Điều này thường liên quan đến chuyển đổi nguồn dữ liệu multicast thành unicast trước khi truyền tới AWS qua [AWS Direct Connect](https://aws.amazon.com/directconnect/). Tuy nhiên, việc thu nhận trực tiếp dữ liệu multicast ngoại vi trên AWS đã đưa ra thách thức đối với nhiều tổ chức. Bài viết này trình bày cách SMC tiếp cận đổi mới để vượt qua các trở ngại đó. Chúng tôi trình bày cách SMC dùng hỗ trợ multicast tích hợp của [AWS Transit Gateway](https://aws.amazon.com/transit-gateway/) để liên lạc trong môi trường [Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) (Amazon VPC), kết hợp với [Fortinet SD-WAN](https://www.fortinet.com/content/dam/fortinet/assets/data-sheets/fortinet_secure_sdwan.pdf) cho giải pháp overlay. Thiết lập này cho phép SMC thiết lập các đường hầm [Generic Routing Encapsulation (GRE)](https://www.rfc-editor.org/rfc/rfc2784) qua Direct Connect, mang nguồn dữ liệu giá multicast từ hệ thống on-premises của họ trực tiếp vào AWS Cloud.

#### **AWS Transit Gateway là gì**

AWS Transit Gateway là một bộ trung chuyển mạng giúp kết nối các VPC và mạng on-premises theo kiểu hub-and-spoke. Nó hỗ trợ nhiều loại kết nối như VPC, [thiết bị SD-WAN](https://docs.aws.amazon.com/vpc/latest/tgw/tgw-connect.html), cổng Direct Connect, kết nối VPN và các Transit Gateway khác. Điều này loại bỏ nhu cầu kết nối điểm-điểm phức tạp. Một chức năng quan trọng là hỗ trợ [multicast](https://docs.aws.amazon.com/vpc/latest/tgw/tgw-multicast-overview.html) native, tự động xử lý định tuyến multicast cho các instance gửi dữ liệu đến nhiều instance nhận thuộc cùng một nhóm multicast.

### **Thách thức**

SMC bắt đầu hành trình trên AWS với triết lý cốt lõi là mang lại “trải nghiệm giao dịch nhanh và liền mạch” cho người dùng cuối. Việc có một nền tảng phát sóng có hiệu suất cao là chìa khóa cho trải nghiệm đó. Vì nền tảng phát sóng nhận sự kiện từ sàn giao dịch chứng khoán và gửi đến các trader, nó là thành phần quan trọng của ứng dụng giao dịch bán lẻ hiện đại.

SMC cần một hệ thống có khả năng cung cấp dữ liệu thị trường tài chính gần như thời gian thực cho trader với mức độ chịu mất gói bằng 0, bởi vì ngay cả một gói lỗi cũng có thể hiển thị thông tin thị trường then chốt sai (như đỉnh giá trong 52 tuần). Điều này có thể gây ra thua lỗ tài chính đáng kể cho trader và ảnh hưởng tới niềm tin của khách hàng. Hạ tầng phát sóng on-premises hiện tại của SMC gặp thách thức về khả năng mở rộng và không đáp ứng được yêu cầu hiệu suất của các ứng dụng giao dịch tài chính hiện đại, khiến downtime thường xuyên và giảm hiệu suất.

### **Tổng quan giải pháp**

Các tổ chức cần kết nối mạng hybrid để liên kết liền mạch các trung tâm dữ liệu on-premises, địa điểm từ xa và hạ tầng cloud. AWS cung cấp [các tùy chọn kết nối](https://docs.aws.amazon.com/whitepapers/latest/hybrid-connectivity/hybrid-network-connections.html) cho các kiến trúc hybrid như Direct Connect và [Site-to-Site VPN](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html), để kết nối tài nguyên on-premises lên AWS an toàn.

SMC hoạt động trong lĩnh vực tài chính có quy định khắt khe, nên khi bắt đầu thiết kế nền tảng broadcast tài chính lai trên AWS Cloud, họ xác định bốn mục tiêu chính:

* Khả năng mở rộng  
* Độ tin cậy  
* Hiệu suất  
* Bảo mật

Để đạt các mục tiêu này ở quy mô lớn, SMC sử dụng [AWS Control Tower](https://aws.amazon.com/controltower/) để thiết lập workloads trên AWS. AWS Control Tower cung cấp cách rõ ràng và hiệu quả để này và quản trị môi trường AWS đa tài khoản an toàn. Nó tạo ra [landing zone](https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-aws-environment/understanding-landing-zones.html) dựa trên best-practices và quản trị thông qua các [controls](https://docs.aws.amazon.com/controltower/latest/userguide/controls.html) từ danh mục có sẵn. Landing zone là nền tảng đa tài khoản theo chuẩn [well-architected](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html), tuân theo best-practices của AWS.

#### **Các cân nhắc thiết kế**

Đáp ứng yêu cầu từ các sàn truyền thống phải kết thúc kết nối mạng dữ liệu giá tại địa điểm on-premises, SMC đánh giá hai phương án kiến trúc:

1. Kết thúc nguồn dữ liệu multicast tại trung tâm dữ liệu, chuyển đổi thành unicast và chuyển giải pháp phát sóng hiện tại lên AWS. Cách này nhanh hơn nhưng mang theo các hạn chế giải pháp cũ lên cloud.  
2. Kết thúc nguồn dữ liệu multicast tại trung tâm dữ liệu và gửi trực tiếp nguồn multicast lên AWS. Cách này cho phép thiết kế lại hệ broadcast bằng các dịch vụ AWS native.

Sau khi cân nhắc, SMC quyết định kiến trúc lại hoàn toàn hệ thống trên AWS. Quyết định chiến lược này dựa vào hai mục tiêu:

1. Xây dựng kiến trúc sẵn sàng cho tương lai  
2. Tối đa hóa hiệu quả với các dịch vụ AWS native

Để đạt các mục tiêu, nền tảng tuân thủ một số nguyên tắc cốt lõi:

**Ưu tiên tính mới của sự kiện hơn sự đầy đủ**

Vì hiệu suất và tính thực tiễn, hệ thống sẽ loại bỏ các sự kiện cũ. Ví dụ, giá giao dịch cuối cùng (LTP) của mã chứng khoán XYZ là 100, 101, 102 lần lượt tại T1, T2, T3, thì hệ thống có thể loại bỏ giá 100 và 101 để hiển thị trực tiếp giá 102\. Người dùng chủ yếu quan tâm đến giá hiện tại hơn các giá cũ khi kiểm tra LTP.

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image.png)

Hình 1 – Giá giao dịch cuối cùng

Tuy nhiên, giá trị lịch sử rất là quan trọng cho việc phân tích như đỉnh/thấp trong 12 tuần, 52 tuần, hoặc xem danh sách tổng hợp lệnh.

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image-1.png)

Hình 2 – Danh sách giá từ cao xuống thấp

Vì vậy, giải pháp cần một chế độ thời gian thực cho dữ liệu giá mới nhất và cơ chế đối chiếu dữ liệu đã loại bỏ/lỗi qua path khác. Để đáp ứng, hệ thống ghi nhận và đối chiếu thời gian thực bằng microservices độc lập và có khả năng mở rộng trên cụm [Amazon Elastic Container Service](https://aws.amazon.com/ecs/) (Amazon ECS), sử dụng dịch vụ AWS native để xử lý:

* [Amazon ElastiCache](https://aws.amazon.com/elasticache/) để cache và phản chiếu packet dữ liệu ghi nhận mới nhất, truy xuất nhanh  
* [Amazon RDS PostgreSQL](https://aws.amazon.com/rds/postgresql/) cho lưu trữ dài hạn và đối chiếu batch

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image-2.png)

Hình 3 – Ghi lại và đối chiếu giá

**Xử lý đa luồng cho throughput cao**

Do khối lượng dữ liệu thị trường lớn, hệ thống xử lý đa luồng trên tất cả các phần. Để hạn chế mất packet do giới hạn băng thông mạng, thiết lập nhiều kết nối TCP ở các port khác nhau trên mỗi instance để truyền dữ liệu song song.

Một thách thức là đảm bảo thứ tự xử lý đúng. Nếu XYZ được update hai lần một giây—M1 (giá lên 100\) và M2 (giá lên 101\) —mà M2 xử lý trước M1 sẽ gây lỗi lớn. Để xử lý, hệ thống thêm thành phần thời gian tùy biến (custom chronological component) trước khi dữ liệu trả về giao diện người dùng.

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image-3.png)

Hình 4 – Sắp xếp dữ liệu theo thứ tự thời gian

**Quản lý kết nối WebSocket ở quy mô lớn**

Công nghệ WebSocket cho phép giao tiếp hai chiều, thời gian thực giữa máy khách và máy chủ, làm cho nó trở nên lý tưởng để phát sóng dữ liệu thị trường đến giao diện web và di động. Không giống như các yêu cầu HTTP truyền thống, các kết nối WebSocket:

* Duy trì kết nối liên tục, giảm latency  
* Giảm tải mạng khi loại bỏ handshake lặp lại  
* Cho phép cập nhật đẩy từ máy chủ (server-push), điều này rất quan trọng đối với việc phân phối dữ liệu thị trường theo thời gian thực  
* Giảm tải máy chủ so với các phương pháp dựa trên thăm dò (polling-based)

SMC đã triển khai các kết nối WebSocket chạy trên các cụm ECS để sử dụng những lợi ích này trên các giao diện ứng dụng web và di động của họ. Tuy nhiên, việc vận hành các hệ thống dựa trên WebSocket ở quy mô lớn đặt ra những thách thức:

**1\. Thách thức về quản lý kết nối**

Khi thiết lập, các client WebSocket duy trì kết nối với các instance server cụ thể. Điều này làm phức tạp quá trình cân bằng tải truyền thống, đặc biệt khi scaling ECS container vì các kết nối hiện tại không dễ chia lại sang các instance mới do trạng thái của chúng.

**2\. Thách thức về “bầy đàn” (thundering herd) của WebSocket**

Trong giờ thị trường, hàng nghìn nhà giao dịch đồng thời cố gắng thiết lập các kết nối WebSocket, đặc biệt là vào thời điểm mở cửa thị trường hoặc sau khi bảo trì hệ thống. Hiệu ứng "thundering herd" này có thể làm quá tải máy chủ và dẫn đến lỗi kết nối. Hơn nữa, khi các container được thay thế trong các sự kiện mở rộng quy mô, nhiều máy khách cố gắng kết nối lại đồng thời có thể tạo ra căng thẳng tương tự trên hệ thống.

Để giải quyết những thách thức này, một chiến lược quản lý kết nối toàn diện đã được triển khai. Điều này bao gồm mở rộng quy mô dựa trên kết nối thông qua [các báo động Amazon CloudWatch tùy chỉnh](https://docs.aws.amazon.com/managedservices/latest/userguide/custom-cloudwatch-events.html) và kết nối lại máy khách theo cấp số nhân (staggered client reconnections) bằng cách sử dụng [exponential backoff and jitter](https://aws.amazon.com/blogs/architecture/exponential-backoff-and-jitter/). Để có khả năng mở rộng dài hạn, nhóm cũng đánh giá các cách tiếp cận thay thế như quản lý trạng thái bên ngoài bằng cách sử dụng [ElastiCache](https://aws.amazon.com/elasticache/redis/) để lưu trữ trạng thái kết nối cho các chuyển đổi máy khách liền mạch giữa các container và [mở rộng quy mô dần](https://aws.amazon.com/blogs/containers/scale-your-amazon-ecs-using-different-aws-native-services/) với các khoảng thời gian được kiểm soát để ngăn chặn sự gia tăng đột biến của kết nối.

**Độ ổn định sản xuất & quan sát**

Để đảm bảo độ tin cậy của hệ thống phát sóng, SMC đã triển khai một công cụ tùy chỉnh sử dụng LGTM stack để giám sát và quan sát toàn diện, kết hợp bốn công cụ chính: [Loki](https://grafana.com/oss/loki/) cho nhật ký, [Grafana](https://grafana.com/docs/grafana/latest/panels-visualizations/visualizations/) để trực quan hóa, [Tempo](https://grafana.com/oss/tempo/) để theo dõi và [Mimir](https://grafana.com/oss/mimir/) for metrics. cho các số liệu. Điều này được tích hợp với một hệ thống thông báo và quản lý sự cố tập trung bằng cách sử dụng [AWS Systems Manager Incident Manager](https://docs.aws.amazon.com/incident-manager/latest/userguide/what-is-incident-manager.html) để nhanh chóng giảm thiểu và phục hồi từ các sự cố ảnh hưởng đến các ứng dụng được lưu trữ trên AWS.

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image-4.png)

Hình 5 – Trình quản lý sự cố tích hợp

### **Kiến trúc giải pháp**

Kiến trúc tham chiếu cấp cao sau đây cho thấy cách SMC triển khai nền tảng phát sóng của họ. AWS Transit Gateway đóng một vai trò quan trọng trong kiến trúc này bằng cách đóng vai trò là bộ định tuyến đám mây giúp hợp lý hóa cấu trúc liên kết mạng, đồng thời cho phép định tuyến multicast trên nhiều VPC. Nó tập trung hóa khả năng kết nối giữa các VPC và mạng on-premises, đồng thời hỗ trợ các kết nối băng thông cao, độ trễ thấp.

Việc sử dụng AWS Transit Gateway đã cho phép SMC mở rộng mạng của họ khi họ thêm các VPC hoặc địa điểm on-premises mới, thực hiện các chính sách mạng nhất quán trên tất cả các mạng được đính kèm và giảm số lượng điểm kết nối cần thiết để kết nối nhiều VPC và mạng on-premises.

SMC đã sử dụng Fortinet Firewall để thu nạp dữ liệu multicast qua các đường hầm GRE trong Amazon VPC. Họ đã tích hợp FortiGate SD-WAN Hub của họ với AWS Transit Gateway để thiết lập kết nối an toàn, hiệu suất cao giữa môi trường on-premises và AWS, cho phép phân phối hiệu quả các nguồn cấp dữ liệu thị trường multicast trên nhiều VPC, hợp lý hóa việc quản lý các kiến trúc mạng phức tạp và giảm chi phí vận hành trong việc quản lý mạng đa VPC.

Cách định cấu hình [FortiGate SD-WAN](https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/504287/sd-wan-designs-and-architectures) nằm ngoài phạm vi thảo luận của bài đăng này, nhưng có thể kiểm tra chi tiết đầy đủ [tại đây](https://aws.amazon.com/blogs/apn/how-to-quickly-and-securely-connect-to-aws-using-fortinet-sd-wan/).

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image-5.png)

Hình 6 – Kiến trúc hệ thống phát sóng

### **Solution Outcome**

Hệ thống mới được thiết kế của SMC trong AWS hiện có thể xử lý hàng chục nghìn người dùng đồng thời. Nó có thể xử lý hơn 100K tin nhắn mỗi giây từ nhiều sàn giao dịch chứng khoán với thời gian ngừng hoạt động bằng không. AWS cho phép SMC mở rộng quy mô nền tảng của họ để đáp ứng nhu cầu kinh doanh gia tăng trong giờ cao điểm, dẫn đến hiệu suất tốt hơn và độ trễ thấp hơn (cải thiện khoảng 60%) và thu nhỏ quy mô liền mạch sau giờ làm việc để tiết kiệm chi phí.

![alt text](/images/3-BlogsTranslated/3.1-Blog1/image-6.png)

Hình 7 – Các chỉ số độ trễ hệ thống

### **Kết luận**

Hành trình của SMC từ nền tảng phát sóng on-premises sang nền tảng cloud-native là một ví dụ điển hình về cách các tổ chức tài chính có thể vượt qua các giới hạn cơ sở hạ tầng truyền thống thông qua việc áp dụng AWS một cách chiến lược. Sự chuyển đổi đòi hỏi những quyết định kiến trúc táo bạo—chọn tái kiến trúc thay vì di chuyển—và chứng minh rằng với việc lập kế hoạch cẩn thận, các dịch vụ AWS phù hợp và cam kết hiện đại hóa, các công ty dịch vụ tài chính có thể xây dựng cơ sở hạ tầng đáp ứng các yêu cầu khắt khe ngày nay đồng thời mở rộng quy mô cho các cơ hội ngày mai.

*Tại [SMC Global Securities](https://www.smctradeonline.com/) (và  [Stoxkart](https://www.stoxkart.com/)), hành trình chuyển đổi kỹ thuật số của chúng tôi với AWS đã tăng cường đáng kể tính ổn định, hiệu suất và sự linh hoạt trong hoạt động của nền tảng. Việc di chuyển từ on-premises lên đám mây đã loại bỏ nhu cầu mở rộng quy mô, vá lỗi và nâng cấp cơ sở hạ tầng thủ công—giải phóng các nhóm của chúng tôi để tập trung vào đổi mới. Với khả năng kiểm soát, khả năng hiển thị được cải thiện và khả năng tự động mở rộng quy mô trong giờ giao dịch cao điểm, chúng tôi đã xây dựng một hệ sinh thái môi giới kiên cường, sẵn sàng cho tương lai, mang lại trải nghiệm liền mạch cho khách hàng của chúng tôi.*

*– Abhishek Chawla (SMC , CTO)*

### **Về các tác giả﻿**

**![Abhishek Sarolia](/images/3-BlogsTranslated/3.1-Blog1/image-7.png)**

### Abhishek Sarolia

Abhishek Sarolia là Kiến trúc sư Giải pháp cấp cao tại AWS. Anh làm việc với người dùng AWS để giải quyết các thách thức kinh doanh của họ bằng cách thiết kế các giải pháp an toàn, hiệu suất cao và khả năng mở rộng sử dụng các công nghệ điện toán đám mây mới nhất. Anh có niềm đam mê với công nghệ và thích xây dựng, thử nghiệm các dự án về AI/ML và IoT. Ngoài công việc, anh yêu thích du lịch, đọc sách phi hư cấu và dành thời gian cho gia đình.

![Abhishek Chawla](/images/3-BlogsTranslated/3.1-Blog1/image-8.png)

### Abhishek Chawla (Khách mời)

Abhishek Chawla là Giám đốc Sản phẩm và Công nghệ Tập đoàn (CPTO) tại SMC Global Securities, nơi anh lãnh đạo chiến lược công nghệ và sản phẩm cho nhiều đơn vị kinh doanh như môi giới dịch vụ đầy đủ (SMC), môi giới môi giới chiết khấu (Stoxkart), quản lý tài sản và phân phối. Với gần hai thập kỷ kinh nghiệm trong các lĩnh vực fintech, edtech, chăm sóc sức khỏe, và du lịch, Abhishek đã thúc đẩy những chuyển đổi kỹ thuật số quy mô lớn bằng cách hiện đại hóa hạ tầng, xây dựng nền tảng cloud-native và mở rộng các nhóm kỹ thuật hiệu suất cao. Anh làm việc chặt chẽ với các CEO để đảm bảo các sáng kiến công nghệ phù hợp với mục tiêu kinh doanh, tạo ra tác động đo lường được thông qua đổi mới, hiệu quả và lấy khách hàng làm trọng tâm.

![Kartik Manimuthu](/images/3-BlogsTranslated/3.1-Blog1/image-9.png)

### Kartik Manimuthu (Khách mời)

Kartik Manimuthu là Giám đốc Kỹ thuật Đám mây tại SMC Global Securities. Với niềm đam mê giải quyết các bài toán kinh doanh phức tạp bằng công nghệ, anh dẫn dắt nhóm kỹ thuật thiết kế các giải pháp sáng tạo, vững chắc giúp thúc đẩy chuyển đổi số của công ty. Kartik chuyên về chuyển đổi lên cloud, hiện đại hóa hạ tầng doanh nghiệp và xây dựng nền tảng có thể mở rộng phù hợp với mục tiêu kinh doanh. Ngoài văn phòng, anh thích khám phá công nghệ mới và đọc sách.

![Digvijay](/images/3-BlogsTranslated/3.1-Blog1/image-10.png)

### Digvijay (Khách mời)

Digvijay là Giám đốc Kỹ thuật tại SMC, một công ty môi giới hàng đầu, nơi anh đã dẫn dắt chiến lược công nghệ và đổi mới sản phẩm trong hai năm qua. Với hơn 10 năm kinh nghiệm trong ngành phần mềm, Digvijay có chuyên môn sâu về xây dựng hệ thống có khả năng mở rộng và lãnh đạo các nhóm kỹ thuật hiệu suất cao. Trước khi gia nhập SMC, Digvijay từng giữ các vị trí kỹ thuật chủ chốt tại Microsoft và Expedia, đóng góp vào các nền tảng lớn phục vụ khách hàng. Quản lý của anh kết hợp nền tảng kỹ thuật vững chắc với hiểu biết sâu về ngành dịch vụ tài chính.

![Avanish Yadav](/images/3-BlogsTranslated/3.1-Blog1/image-11.png)

### Avanish Yadav

Avanish Yadav là Kiến trúc sư Giải pháp Mạng cấp cao tại AWS. Với niềm đam mê về công nghệ mạng, anh thích sáng tạo và hỗ trợ người dùng giải quyết các vấn đề kỹ thuật phức tạp bằng cách xây dựng các kiến trúc điện toán đám mây an toàn, khả năng mở rộng. Khi không cộng tác với người dùng để cung cấp giải pháp chuyên sâu, anh thường chơi cricket bên ngoài công việc. LinkedIn: /avanish-yadav-93b8a947/.