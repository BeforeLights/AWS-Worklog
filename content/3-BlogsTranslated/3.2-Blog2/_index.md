---
title: "Blog 2"
date: "2000-01-01"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# **Optimize security operations with AWS Security Incident Response**

bởi Kyle Shields và Matt Meck vào ngày 23/09/2005 trong [Best Practices](https://aws.amazon.com/blogs/security/category/post-types/best-practices/), [Customer Solutions](https://aws.amazon.com/blogs/security/category/post-types/customer-solutions/), [Security, Identity, & Compliance](https://aws.amazon.com/blogs/security/category/security-identity-compliance/), [Technical How-to](https://aws.amazon.com/blogs/security/category/post-types/technical-how-to/) | [Permalink](https://aws.amazon.com/blogs/security/optimize-security-operations-with-aws-security-incident-response/) | [Comments](https://aws.amazon.com/blogs/security/optimize-security-operations-with-aws-security-incident-response/#Comments)

Các mối đe dọa bảo mật yêu cầu hành động nhanh chóng, đó là lý do [AWS Security Incident Response](https://aws.amazon.com/security-incident-response/) cung cấp bảo vệ gốc AWS có thể ngay lập tức củng cố tư thế bảo mật của bạn. Giải pháp toàn diện này kết hợp logic tự động phân loại và đánh giá với metadata chu vi bảo mật của bạn để xác định các vấn đề quan trọng, liền mạch bổ sung chuyên môn con người khi cần. Khi Security Incident Response được tích hợp với [Amazon GuardDuty](https://aws.amazon.com/guardduty) và [AWS Security Hub](https://aws.amazon.com/security-hub) trong một môi trường bảo mật hợp nhất, tổ chức có quyền truy cập 24/7 vào [AWS Customer Incident Response Team](https://docs.aws.amazon.com/security-ir/latest/userguide/understand-response-teams-and-support.html) (CIRT) để phát hiện nhanh chóng, phân tích chuyên môn, và ngăn chặn đe dọa hiệu quả—quản lý qua một bảng điều khiển trực quan. Security Incident Response bao gồm trong [Amazon Managed Services (AMS)](https://aws.amazon.com/managed-services/), giúp tổ chức áp dụng và vận hành AWS ở quy mô lớn một cách hiệu quả và an toàn.

Trong bài này, chúng tôi hướng dẫn bạn kích hoạt Security Incident Response và thực hiện bằng chứng khái niệm (POC) để nhanh chóng nâng cao khả năng bảo mật khi nhận lợi ích ngay lập tức. Chúng tôi khám phá chức năng dịch vụ, thiết lập tiêu chí thành công POC, xác định cấu hình, chuẩn bị triển khai, kích hoạt dịch vụ và tối ưu hiệu quả từ ngày đầu tiên, giúp tổ chức bạn xây dựng niềm tin trong suốt vòng đời phản ứng sự cố đồng thời cải thiện thời gian phục hồi.

## **Hiểu chức năng của Security Incident Response**

Dịch vụ AWS Security Incident Response cung cấp khả năng phát hiện và phản ứng mối đe dọa toàn diện thông qua quy trình bốn bước hợp lý. Nó bắt đầu bằng việc lấy các phát hiện bảo mật từ GuardDuty và các tích hợp Security Hub được chọn với công cụ bên thứ ba. Dịch vụ tự động phân loại các phát hiện này bằng metadata khách hàng và tình báo đe dọa để xác định hành vi bất thường và hoạt động nghi ngờ. Khi phát hiện mối đe dọa tiềm ẩn, thành viên CIRT chủ động điều tra các trường hợp qua portal khách hàng để xác định đó là tích cực thật hay giả. Với các mối đe dọa được xác nhận, dịch vụ leo thang các phát hiện để hành động ngay lập tức, trong khi với tích cực giả sẽ cập nhật hệ thống phân loại tự động và quy tắc triệt tiêu cho GuardDuty và Security Hub, liên tục cải thiện độ chính xác phát hiện.

## **Bảo vệ toàn diện với ít điều kiện tiên quyết**

Security Incident Response mang lại năng lực bảo mật mạnh mẽ nhờ tích hợp liền mạch với cả [hệ thống phát hiện và phản ứng sự cố AWS](https://aws.amazon.com/premiumsupport/aws-incident-detection-response) (TDIR) và dịch vụ bảo mật bên thứ ba như CrowdStrike, Lacework, TrendMicro. Giải pháp này cung cấp trung tâm chỉ huy thống nhất để quản lý sự cố đầu-cuối—từ lập kế hoạch, giao tiếp đến giải quyết—khi lấy các phát hiện GuardDuty và tích hợp với nhà cung cấp ngoài qua Security Hub. Với quản lý case an toàn cùng timeline hoạt động bất biến, nó nâng cao đáng kể hoạt động bảo mật khi tăng cường các đội SOC và phản ứng sự cố (IR) bằng khả năng hiển thị tốt hơn cũng như quyền truy cập vào các công cụ và nhân sự đã kiểm chứng từ AWS. CIRT AWS cộng tác với đội ứng phó của bạn trong truy vết và phục hồi, giải phóng nguồn lực có giá trị cho các ưu tiên khác.

Dịch vụ cung cấp giá trị liên tục qua khả năng giám sát và phản ứng chủ động. Nó liên tục giám sát môi trường của bạn bằng các phát hiện từ GuardDuty và Security Hub, với tự động hóa dịch vụ, phân loại và phân tích làm việc âm thầm để cảnh báo bạn chỉ trong trường hợp có mối bận tâm bảo mật thực sự. Bảo vệ này mang lại giá trị tức thì lúc xảy ra sự cố tiềm năng mà không đòi hỏi bạn phải chú ý liên tục.

Bắt đầu rất đơn giản—điều kiện duy nhất là bật  [AWS Organizations](https://aws.amazon.com/organizations/) và bảo đảm rằng bạn đã thiết lập Organizations với cấu trúc đơn vị tổ chức (OU) cơ bản gồm các tài khoản thành viên. Nền tảng này vừa cho phép triển khai Security Incident Response, vừa là nền tảng vững chắc cho chiến lược TDIR mạnh ở toàn tổ chức.

## **Xác định tiêu chí thành công**

Thiết lập tiêu chí thành công giúp so sánh kết quả POC với mục tiêu kinh doanh. Một số ví dụ:

* **Chỉ định đội phản ứng sự cố:** Xác định và ghi chép thành viên đội nội bộ cũng như nguồn lực ngoài chịu trách nhiệm phản ứng sự cố. Như nhấn mạnh trong [AWS Well-Architected Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/sec_incident_response_identify_personnel.html), có nhân sự chỉ định sẽ giảm thời gian phân loại và phản ứng khi sự cố xảy ra.  
* **Phát triển framework phản ứng sự cố chính thức:** Xây dựng kế hoạch phản ứng sự cố toàn diện với playbook chi tiết cùng quy trình tập luyện tabletop thường xuyên. AWS cung cấp thư viện playbook tham khảo trên [GitHub](https://github.com/aws-samples/aws-customer-playbook-framework).  
* **Chạy bài tập tabletop:** Xem xét thực hiện mô phỏng thường xuyên để kiểm tra kế hoạch phản ứng sự cố, phát hiện lỗ hổng, xây dựng “bản năng hành động” cho đội trước khi khủng hoảng thực sự xảy ra. AWS cung cấp ngữ cảnh về các loại [bài tập tabletop](https://docs.aws.amazon.com/security-ir/latest/userguide/types-of-simulations.html).  
* **Xác định các nhà cung cấp bảo mật bên thứ ba hiện có:** Xác định nhà cung cấp tích hợp Security Hub đẩy dữ liệu vào Security Incident Response. Đối tác AWS cung cấp phát hiện như tài liệu ở [Detect and Analyze](https://docs.aws.amazon.com/security-ir/latest/userguide/detect-and-analyze.html).  
* **Triển khai GuardDuty:** Cấu hình GuardDuty theo thực hành tốt nhất để giám sát—phát hiện đe dọa trên dịch vụ trọng yếu. AWS duy trì thực hành tốt nhất GuardDuty tại [AWS Security Services Best Practices for GuardDuty](https://aws.github.io/aws-security-services-best-practices/guides/guardduty/).

Kiểm tra tiêu chí thành công của bạn để đảm bảo mục tiêu thực tế với thời gian cũng như ràng buộc đặc thù tổ chức. Ví dụ: Bạn có kiểm soát hoàn toàn cấu hình dịch vụ AWS không? Có nguồn lực có thể dành thời gian thực thi và kiểm tra không? Thời điểm này có thuận tiện để các bên liên quan đánh giá dịch vụ không?

## **Định nghĩa cấu hình Security Incident Response**

Sau khi xác định tiêu chí và thời gian, bạn nên định nghĩa cấu hình Security Incident Response. Một số quyết định quan trọng gồm:

* **Chọn tài khoản quản trị viên được ủy quyền:** Xác định tài khoản làm quản trị viên được ủy quyền (DA). Tài khoản này và AWS Region đã chọn sẽ lưu trữ dịch vụ và portal Security Incident Response. [AWS Security Reference Architecture (SRA)](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/welcome.html) đề nghị dùng tài khoản công cụ bảo mật chuyên biệt. Xem [các lưu ý nên cân nhắc](https://docs.aws.amazon.com/security-ir/latest/userguide/considerations_important.html) trước khi chốt DA.  
* **Định nghĩa phạm vi tài khoản:** Security Incident Response là dịch vụ cấp tổ chức. Mỗi tài khoản ở mọi Region trong tổ chức đều nằm trong bảo hiểm dưới một đăng ký duy nhất. Bảo hiểm tự động điều chỉnh khi thêm/xóa tài khoản, bảo vệ toàn diện AWS footprint.  
* **Cấu hình nguồn phát hiện:** Xác định các phát hiện đáp ứng nhu cầu tổ chức. Dịch vụ mặc định lấy phát hiện GuardDuty toàn tổ chức và một số loại phát hiện Security Hub từ đối tác bên thứ ba. Đánh giá kế hoạch bảo vệ GuardDuty và phát hiện Security Hub hữu ích nhất cho tư thế bảo mật, khả năng phản ứng sự cố của bạn.  
* **Xây dựng framework leo thang:** Thiết lập ngưỡng leo thang rõ ràng cho từng loại trường hợp: tự quản lý, có hỗ trợ AWS, chủ động. Ai có quyền xác định gửi loại case nào dựa trên mức độ nghiêm trọng, tác động, yêu cầu nguồn lực.  
* Triển khai chiến lược phân tích: Xác định dùng công cụ phân tích AWS gốc như [Amazon Athena](https://aws.amazon.com/athena/), [Amazon OpenSearch](https://aws.amazon.com/opensearch-service/), và [Amazon Detective](https://aws.amazon.com/detective/)), hoặc tích hợp SIEM (security information and event management) hiện có. Chức năng này làm giàu phản ứng sự cố với dữ liệu bối cảnh, hiểu biết sâu hơn.

## **Chuẩn bị triển khai**

Sau khi xác định tiêu chí, cấu hình, bạn xác định các bên liên quan, trạng thái và thời gian mong muốn. Chuẩn bị triển khai bằng cách:

* Kế hoạch dự án, timeline: Xây dựng kế hoạch, tiêu chí thành công, phạm vi, mốc chính, thời gian triển khai thực tế. Đề xuất dòng thời gian:  
  * Trước khi bật:  
    * Cấu hình GuardDuty, các bên thứ ba Security Hub, lên kế hoạch tài nguyên  
    * Xin phê duyệt thử nghiệm POC từ đội tài khoản AWS hay đội Dịch vụ  
  * Ngày 0 – Bật dịch vụ  
  * Tuần 1 – Mở các case CIRT phản ứng  
  * Tuần 2 – Kết nối công cụ ITSM  
  * Tuần 3 – Tập luyện tabletop  
  * Tuần 4 – Rà soát báo cáo CIRT cung cấp  
* Xác định các bên liên quan: CISO, nhóm bảo mật thông tin, SOC, đội phản ứng sự cố, kỹ sư bảo mật, tài chính, pháp lý, tuân thủ, MSSP ngoài, đại diện business unit.  
* Phát triển ma trận RACI: Vẽ biểu đồ RACI xác định vai trò, trách nhiệm, tạo thuận lợi cho trách nhiệm giải trình, kênh giao tiếp phù hợp.  
* Cấu hình quyền truy cập tài khoản quản lý: Đảm bảo ủy quyền để phân quyền quản trị. Xem thêm [Permissions required to designate a delegated Security Incident Response administrator account](https://docs.aws.amazon.com/security-ir/latest/userguide/organizations_permissions.html).  
* Thiết lập vai trò IAM/quyền: Dùng [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam) để áp dụng kiểm soát truy cập dựa trên vai trò (kết nối RACI chart), gồm quản lý case, leo thang, vai trò chỉ đọc sử dụng chính sách quản lý AWS. Chi tiết ở [AWS Managed Policies](https://docs.aws.amazon.com/security-ir/latest/userguide/aws-managed-policies.html)

## **Kích hoạt Security Incident Response**

Khi chuẩn bị xong, bạn đã sẵn sàng bật dịch vụ.

**Truy cập Security Incident Response trong tài khoản quản lý:**

1. Vào tài khoản quản lý tổ chức, truy cập AWS Management Console, tìm **Security Incident Response** trên thanh tìm kiếm.  
2. Chọn **Sign up**.  
3. Đảm bảo đã chọn **Use delegated administrator account** (khuyên dùng), nhập số tài khoản quản trị vào trường **Account ID**, chọn **Next**.  
4. Đăng nhập vào tài khoản quản trị được ủy quyền đã cấu hình ở bước 3, tìm **Security Incident Response** rồi chọn **Sign up**.

**Hoàn thành thiết lập ở tài khoản quản trị viên được ủy quyền:**

1. Định nghĩa chi tiết thành viên:  
   1. Chọn vùng nhà của bạn dưới **Region selection**.  
   2. Đối với **Membership name**, nhập một tên phù hợp tuân theo tiêu chuẩn đặt tên của tổ chức bạn.  
   3. Dưới **Membership contacts**, nhập thông tin **Primary** và **Secondary contact**.  
2. Thêm **Membership tags** theo chiến lược gắn thẻ của tổ chức bạn.  
3. Chọn **Next**.  
4. Cấu hình quyền cho phản ứng chủ động:  
   1. **Service permissions for proactive response** đã được kích hoạt, nhưng bạn có thể vô hiệu hóa tính năng này nếu cần.  
   2. Chọn **By choosing this option…** và chọn **Next**.  
   3. Xem xét quyền dịch vụ và chọn **Next**.  
5. Xem xét cấu hình thành viên và chi tiết, sau đó chọn **Sign up**.  
6. Vai trò liên kết dịch vụ được tạo với phản ứng chủ động không thể được tạo trong tài khoản quản lý thông qua quy trình lên tàu này. Xem [AWS Security Incident Response User Guide](https://docs.aws.amazon.com/security-ir/latest/userguide/working-with-stacksets.html) để triển khai vai trò liên kết dịch vụ đến tài khoản quản lý.

Xem hướng dẫn chi tiết ở [video hướng dẫn thiết lập trên YouTube.](https://www.youtube.com/watch?v=NSyUlhDc_d0).

Nhiều tổ chức có các quy trình và bộ ứng dụng được thiết lập tốt cho IR và quản lý mối đe dọa bảo mật. Để phù hợp với các thiết lập có sẵn này, AWS đã phát triển các tích hợp với các ứng dụng ITSM và quản lý trường hợp phổ biến. Các bản phát hành ban đầu của chúng tôi cho phép tích hợp hai chiều hoàn toàn với cả Jira và ServiceNow, với nhiều hơn nữa đang trên đường.

Chúng tôi đã cung cấp hướng dẫn đầy đủ quy trình thiết lập tại [GitHub](https://github.com/aws-samples/sample-aws-security-incident-response-integrations).

## **Tối ưu hóa giá trị từ ngày đầu tiên**

 Ngay sau khi kích hoạt dịch vụ, Security Incident Response bắt đầu thu thập các phát hiện GuardDuty và Security Hub (từ các đối tác bảo mật) của bạn. Các phát hiện của bạn được tự động phân loại và giám sát bằng cách sử dụng logic đánh giá xác định; dựa trên metadata độc đáo của tổ chức bạn và chu vi bảo mật, các mối đe dọa có mức độ ưu tiên cao được leo thang đến trung tâm chỉ huy Security Incident Response của bạn để điều tra ngay lập tức. Trong khi tổ chức của bạn nhận được bảo hiểm 24/7 từ đầu, việc thực hiện các tối ưu hóa được khuyến nghị này sẽ tăng cường đáng kể độ chính xác phát hiện mối đe dọa, giảm tích cực giả, tăng tốc thời gian phản ứng và tăng cường tư thế bảo mật tổng thể của bạn thông qua bảo vệ tùy chỉnh được căn chỉnh với rủi ro kinh doanh cụ thể và yêu cầu tuân thủ của bạn.

Để tối đa hóa giá trị ngay lập tức từ Security Incident Response, chúng tôi đề xuất sử dụng khả năng phản ứng của nó bắt đầu từ ngày một. Khi đội của bạn gặp phải hoạt động đáng ngờ hoặc yêu cầu điều tra chuyên môn, bạn có thể tạo một trường hợp được AWS hỗ trợ thông qua cổng thông tin dịch vụ để tương tác trực tiếp với các chuyên gia AWS CIRT. Các chuyên gia bảo mật này một cách hiệu quả mở rộng khả năng của đội bạn, cung cấp kiến thức chuyên môn và hướng dẫn để giúp bạn nhanh chóng hiểu, ngăn chặn và khắc phục các mối quan tâm bảo mật tiềm ẩn. Quyền truy cập theo yêu cầu này vào AWS CIRT có thể giảm thời gian giải quyết trung bình của bạn, giảm thiểu tác động tiềm ẩn và đảm bảo bạn có hỗ trợ chuyên nghiệp ngay cả đối với các kịch bản bảo mật phức tạp có thể khác làm choáng ngợp tài nguyên nội bộ.

Ví dụ truy vấn hỗ trợ phản ứng:

* Phát hiện IP đáng ngờ trong môi trường, thực hiện các API call đa dạng. Bạn hỗ trợ điều tra được không?  
* Tài khoản mới tạo 2 ngày trước, được thông báo qua quy tắc [Amazon EventBridge](https://aws.amazon.com/eventbridge) và tích hợp endpoint detection response (EDR), bạn giúp xác định phạm vi, tìm ai tạo? Tạo bằng cách nào?  
* Người dùng [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam) thực hiện API call xuyên Region, tạo resource ở Region không dùng.  
* Giải pháp EDR phát hiện hành vi bất thường trên website production, cho thấy vi phạm tiềm tàng.  
* EDR phát hiện tải web-shell nghi ngờ và hoạt động – cần giúp điều tra, cô lập.  
* Người dùng trái phép thực hiện API ngoài quyền hạn—hỗ trợ phát hiện leo thang quyền.  
* Cần giúp phân tích log bảo mật từ [AWS WAF](https://aws.amazon.com/waf) và [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2) instances. Có chỉ số compromise hoặc mẫu lạ không?

## **Các bước tiếp theo**

Nếu bạn quyết định tiến hành với AWS Security Incident Response và triển khai một POC, chúng tôi khuyến nghị các mục hành động sau:

* Xác định xem bạn có phê duyệt và ngân sách để sử dụng Security Incident Response không. Các thỏa thuận giá ưu đãi, giảm giá và thử nghiệm dựa trên hiệu suất có sẵn.  
* Cấu hình và triển khai GuardDuty để giúp duy trì bảo hiểm toàn diện và có liên quan trên các tài khoản quản lý và thành viên, dịch vụ quan trọng và workload của bạn.  
* Xác minh rằng các công cụ bảo mật bên thứ ba (như CrowdStrike, Lacework hoặc Trend Micro) được tích hợp đúng cách với Security Hub.  
* Giao tiếp các thay đổi công cụ phản ứng sự cố bảo mật với các đội tổ chức có liên quan.

## **Kết luận**

Trong bài viết này, chúng tôi đã chỉ cho bạn cách lập kế hoạch và thực hiện một POC AWS Security Incident Response. Bạn đã học cách làm như vậy thông qua các giai đoạn, bao gồm xác định tiêu chí thành công, cấu hình Security Incident Response và xác thực rằng Security Incident Response đáp ứng nhu cầu kinh doanh của bạn.

Là một khách hàng, hướng dẫn này sẽ giúp bạn chạy một POC thành công với Security Incident Response. Nó hướng dẫn bạn đánh giá giá trị và các yếu tố để xem xét khi quyết định thực hiện các tính năng hiện tại.

## **Tài nguyên bổ sung**

* [Security Incident Response – Getting Started Guide](https://docs.aws.amazon.com/security-ir/latest/userguide/getting-started.html)  
* [Configuring security tool integrations through Security Hub](https://docs.aws.amazon.com/security-ir/latest/userguide/detect-and-analyze.html)  
* [Managing Security Incident Response events with Amazon EventBridge](https://docs.aws.amazon.com/security-ir/latest/userguide/eventbridge-integration-full.html)  
* [Amazon GuardDuty best practices](https://aws.github.io/aws-security-services-best-practices/guides/guardduty/)  
* [AWS Security Hub best practices](https://aws.github.io/aws-security-services-best-practices/guides/security-hub/)  
* [AWS Security Incident Response Technical Guide (best practices)](https://docs.aws.amazon.com/security-ir/latest/userguide/security-incident-response-guide.html#:~:text=Train%20incident%20response%20staff,Containment)  
* [AWS Managed Services Offering](https://aws.amazon.com/managed-services/)  
* [AWS Security Incident Response Blog: The customer’s journey to accelerating the incident Response lifecycle](https://aws.amazon.com/blogs/security/aws-security-incident-response-the-customers-journey-to-accelerating-the-incident-response-lifecycle/)

Nếu có phản hồi về bài này, gửi bình luận ở Comments. Nếu có câu hỏi về bài này, hãy [liên hệ AWS Support](https://console.aws.amazon.com/support/home).  
 

![Kyle Shields](../3.2-Blog2/image.png)
Kyle Shields

Kyle là Kiến trúc sư Giải pháp Chuyên gia Bảo mật tập trung phát hiện mối đe dọa và phản ứng sự cố tại AWS. Hiện nay, anh giúp khách hàng doanh nghiệp AWS vận hành Security Incident Response, cải thiện tư thế bảo mật.

![Matt Meck](../3.2-Blog2/image-1.png)
Matt Meck

Matt là chuyên gia bảo mật WW với 10 năm kinh nghiệm trong công nghệ AI, an ninh mạng, 3 năm tại AWS về Lĩnh vực Detection & Response. Đặt ở NY, yêu thích thiên nhiên, anh dành thời gian chơi bóng đá, trượt tuyết, chinh phục các đỉnh núi mới.