---
title: "Blog 3"
date: "2000-01-01"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# **Giải phóng giá trị dữ liệu phi cấu trúc với Amazon Bedrock Data Automation**

bởi Vani Eswarappa và Rupesh Mishra vào ngày 29/09/2025 trong [Amazon Bedrock Knowledge Bases](https://aws.amazon.com/blogs/industries/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-knowledge-bases/), [Amazon Comprehend](https://aws.amazon.com/blogs/industries/category/artificial-intelligence/amazon-comprehend/), [Amazon DataZone](https://aws.amazon.com/blogs/industries/category/analytics/amazon-datazone/), [Amazon EventBridge](https://aws.amazon.com/blogs/industries/category/application-integration/amazon-eventbridge/), [Amazon OpenSearch Service](https://aws.amazon.com/blogs/industries/category/analytics/amazon-elasticsearch-service/), [Amazon Rekognition](https://aws.amazon.com/blogs/industries/category/artificial-intelligence/amazon-rekognition/), [Amazon Simple Storage Service (S3)](https://aws.amazon.com/blogs/industries/category/storage/amazon-simple-storage-services-s3/), [Amazon Textract](https://aws.amazon.com/blogs/industries/category/artificial-intelligence/amazon-textract/), [AWS Glue](https://aws.amazon.com/blogs/industries/category/analytics/aws-glue/), [AWS Lambda](https://aws.amazon.com/blogs/industries/category/compute/aws-lambda/), [AWS Marketplace](https://aws.amazon.com/blogs/industries/category/software/aws-marketplace/), [Healthcare](https://aws.amazon.com/blogs/industries/category/industries/healthcare/), [Industries](https://aws.amazon.com/blogs/industries/category/industries/) | [Permalink](https://aws.amazon.com/blogs/industries/unlocking-the-value-of-unstructured-data-with-amazon-bedrock-data-automation/)

Các tổ chức trong mọi ngành đang gặp khó khăn với sự gia tăng dữ liệu phi cấu trúc—hình ảnh, tài liệu văn bản, PDF, tệp âm thanh & video, và các định dạng chuyên biệt như chuỗi gen. Khác với dữ liệu có cấu trúc, dữ liệu phi cấu trúc thường thiếu tổ chức chuẩn hóa, khiến việc phát hiện, truy cập, và khai phá ý nghĩa từ nguồn dữ liệu giá trị này trở nên khó khăn.a

Tại Amazon Web Services (AWS), chúng tôi ghi nhận những khó khăn tương tự ở các viện nghiên cứu và các tổ chức y tế khi tìm giải pháp lưu trữ, tìm kiếm và khai thác kho dữ liệu phi cấu trúc của mình.

Chúng tôi sẽ khám phá cách giải pháp sử dụng [Amazon Bedrock Data Automation](https://aws.amazon.com/bedrock/bda/), một tính năng của [Amazon Bedrock](https://aws.amazon.com/bedrock/), có thể mang lại:

* Giải pháp tổng thể để quản lý dữ liệu phi cấu trúc  
* Tự động hóa quá trình lưu trữ dữ liệu  
* Cải thiện chất lượng dữ liệu  
* Triển khai chính sách quản trị  
* Truy cập nhanh các sản phẩm dữ liệu giá trị

Chúng tôi cũng làm rõ cách AWS và giải pháp đối tác giúp xử lý khử định danh (de-identification) cho dữ liệu phi cấu trúc, bằng cách làm mờ hoặc xóa thông tin nhận diện khỏi văn bản, PDF, hình ảnh và tài liệu khác. Và vì khử định danh đôi khi cần thiết cho phát triển AI, nghiên cứu, chính sách công và các ứng dụng khác.

## **Thách thức quản lý dữ liệu phi cấu trúc**

Khách hàng các ngành chia sẻ những thách thức cơ bản liên quan đến tổ chức dữ liệu, tích hợp và khả năng truy cập. Chúng tôi đã nhận diện nhiều khó khăn phổ biến mà tổ chức phải đối mặt với dữ liệu phi cấu trúc:

1. Lưu trữ phân mảnh: Dữ liệu bị phân tán trên các storage bucket, workspace cục bộ, hệ thống file và các giải pháp lưu trữ khác nhau.  
2. Khả năng phát hiện hạn chế: Nếu thiếu metadata phù hợp, việc trích xuất và catalog hóa dữ liệu phi cấu trúc giá trị sẽ làm các tài sản bị ẩn và không được khai thác hết tiềm năng.  
3. Tính phức tạp khi tích hợp: Khó kết nối thông tin liên quan giữa các loại dữ liệu đa phương thức.  
4. Vấn đề về quản trị: Khi khối lượng dữ liệu tăng, việc đảm bảo lineage, kiểm soát truy cập và governance ngày càng khó khăn.  
5. Khử định danh dữ liệu: Việc cân bằng nhu cầu insight từ dữ liệu với yêu cầu nghiêm ngặt về riêng tư & tuân thủ là thách thức lớn ở nhiều ngành, đặc biệt khi cần độ chính xác đáp ứng quy định pháp lý.

## **Amazon Bedrock Data Automation cho catalog hóa dữ liệu phi cấu trúc**

[Amazon Bedrock Data Automation](https://docs.aws.amazon.com/bedrock/latest/userguide/bda-how-it-works.html) là một tính năng mạnh mẽ của Amazon Bedrock, dùng để tự động phân loại, tìm kiếm, và trích xuất insight từ dữ liệu đa phương thức phi cấu trúc như tài liệu, hình ảnh, audio và video bằng AI. Hãy xem nó đáp ứng những vấn đề then chốt như thế nào.

Bedrock Data Automation giúp chuẩn hóa quá trình trích xuất insight giá trị từ các loại dữ liệu phi cấu trúc như hình ảnh y tế, báo cáo hồ sơ bệnh án (PDF, hình ảnh), tệp audio & video. Dịch vụ này trích xuất metadata kỹ thuật và kinh doanh qua blueprint tùy chỉnh, giúp dữ liệu phi cấu trúc được phát hiện dễ dàng nhờ khả năng tìm kiếm toàn diện. Đối với các tổ chức nghiên cứu/y tế, điều này nghĩa là hình ảnh, bản scan và dữ liệu nghiên cứu có thể catalog hóa tự động và tìm kiếm dễ dàng mà không cần gán tag thủ công.

Khi tích hợp với các dịch vụ AWS khác (như [AWS Glue](https://aws.amazon.com/glue/) và [Amazon SageMaker Unified Studio](https://aws.amazon.com/sagemaker/unified-studio/)), Bedrock Data Automation tạo điều kiện xây dựng giải pháp phân tích tổng thể qua cái nhìn tích hợp cho các tài sản dữ liệu vốn trước đây bị silo hóa.

![alt text](/images/3-BlogsTranslated/3.3-Blog3/image.png)

*Figure 1 – Giải pháp kiến trúc lưu trữ dữ liệu phi cấu trúc cấp cao*

## ***Giải pháp catalog hóa dữ liệu phi cấu trúc: Cách hoạt động***

*Giải pháp sử dụng kiến trúc nhiều tầng. Dưới đây là explanation flow trình bày ở Figure 1\.*

***1 – Quá trình nạp dữ liệu và khử định danh ban đầu***  
*Dữ liệu từ các nguồn phi cấu trúc, đa phương thức sẽ được chuyển sang Amazon Simple Storage Service ([Amazon S3](https://aws.amazon.com/s3/)), đóng vai trò điểm ingest dữ liệu chính. AWS cung cấp một danh mục dịch vụ chuyển dữ liệu dùng để truyền dữ liệu từ nhiều nguồn doanh nghiệp phi cấu trúc đến Amazon S3 và các dịch vụ AWS khác.*

*Đối với các tổ chức cần dữ liệu đã khử định danh cho các trường hợp sử dụng khác nhau, có thể sử dụng kiến trúc event-driven kết hợp Amazon EventBridge và [AWS Lambda](https://aws.amazon.com/lambda/). Họ có thể gọi các dịch vụ khử định danh AWS và các giải pháp trên AWS Marketplace để khử định danh dữ liệu.*

*Tổ chức cũng có thể tự phát triển giải pháp khử định danh trên AWS bằng cách kết hợp nhiều dịch vụ AWS. Có nhiều lựa chọn hỗ trợ như [Amazon Textract](https://aws.amazon.com/textract/), [Amazon Comprehend](https://aws.amazon.com/comprehend/), AWS Glue, [Amazon Rekognition](https://aws.amazon.com/rekognition/), Amazon Bedrock và các dịch vụ khác. Dữ liệu đã khử định danh sẽ được lưu vào Amazon S3.*

[*AWS Marketplace*](https://aws.amazon.com/marketplace/?nc2=h_rsc_cs_mp) *cung cấp một catalog số hóa các giải pháp bên thứ ba đã được xác minh cho các tình huống khử định danh ở nhiều ngành khác nhau. Ví dụ, với ngành healthcare, AWS Marketplace có các giải pháp đối tác cho [clinical text deidentification](https://aws.amazon.com/marketplace/search/results?prevFilters=%257B%2522nc2%2522%3A%2522h_rsc_cs_mp%2522%257D&searchTerms=deidentification), [PDF deidentification](https://aws.amazon.com/marketplace/search/results?prevFilters=%257B%2522nc2%2522%3A%2522h_rsc_cs_mp%2522%257D&searchTerms=PDF+deidentification) và [DICOM image and metadata deidentification](https://aws.amazon.com/marketplace/search/results?prevFilters=%257B%2522nc2%2522%3A%2522h_rsc_cs_mp%2522%257D&searchTerms=DICOM+image+and+metadata+deidentification)... Các giải pháp này có thể triển khai cho các transform jobs theo thời gian thực hoặc batch với các lựa chọn khác nhau trên AWS.*

***2 – Data processing pipeline***  
*Amazon S3 kích hoạt các events qua Amazon EventBridge, đây là pha xử lý tiếp theo. [Amazon EventBridge](https://aws.amazon.com/eventbridge/) quản lý workflow event-driven và quá trình tự động hóa. EventBridge sẽ gọi Lambda functions để xử lý dữ liệu đã khử định danh và tiếp tục gọi Bedrock Data Automation để xử lý tài liệu, hình ảnh, file audio và video phi cấu trúc.*

*Bedrock Data Automation cung cấp năng lực AI qua foundation models cùng các tính năng tự động hóa dữ liệu. Nó trích xuất metadata mặc định và metadata tuỳ chỉnh bằng blueprint do khách hàng cung cấp. Dữ liệu xử lý sẽ lưu vào một S3 bucket. Ngoài ra, Bedrock Data Automation có thể tiếp tục kích hoạt EventBridge cho các xử lý downstream với dữ liệu và metadata đã trích xuất.*

***3 – Knowledge management***  
*Dữ liệu đã xử lý từ Amazon S3 sẽ chuyển vào [Amazon Bedrock Knowledge Bases](https://aws.amazon.com/bedrock/knowledge-bases/). Ứng dụng Generative AI và chatbot cung cấp giao diện tương tác ngôn ngữ tự nhiên và phản hồi tự động, giúp dữ liệu trở nên dễ truy cập và hành động cho người dùng cuối.*

***4 – Centralized data storage and distribution layer***  
*Chúng tôi sử dụng nhiều tầng lưu trữ để phục vụ các nhu cầu khác nhau của khách hàng. Khi triển khai ứng dụng Generative AI và chatbot, chúng tôi lưu dữ liệu xử lý từ Amazon S3 vào Amazon Bedrock Knowledge Bases. Để xây dựng centralized metadata store, AWS Glue ETL jobs sẽ xử lý dữ liệu incoming từ Bedrock Data Automation, trích xuất metadata và lưu vào một [AWS Glue Catalog](https://docs.aws.amazon.com/glue/latest/dg/start-data-catalog.html).*

[*Amazon DataZone*](https://aws.amazon.com/datazone/) *nhập metadata từ AWS Glue Catalog và cung cấp một portal hợp nhất cho người dùng khám phá, chia sẻ, quản trị dữ liệu dù lưu trữ ở đâu. Nó dùng data catalog để cung cấp repository trung tâm cho metadata và ngữ cảnh vận hành của tài sản dữ liệu. Người dùng có thể khám phá, hiểu tài sản từ nhiều nguồn dữ liệu khác nhau. Ngoài ra, chúng tôi sử dụng [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)  làm storage layer cho metadata, tích hợp với [Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/).*

***5 – Analytics layer***  
*Khi các tài sản đã nằm trong catalog DataZone, người dùng có thể truy vấn, phân tích dữ liệu đó bằng Amazon Athena hoặc Amazon Redshift Query Editor. Điều này cho phép thực hiện analytics phức tạp quy mô lớn và toàn diện về hoạt động business intelligence. Việc tích hợp [Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/) với DynamoDB cung cấp năng lực tìm kiếm mạnh mẽ và khả năng phân tích gần real-time.*

## ***Bảo mật và tuân thủ***

 *Kiến trúc giải pháp này đảm bảo dữ liệu PHI (Protected Health Information) được khử định danh đúng chuẩn trước khi xử lý tiếp. Sử dụng lưu trữ riêng cho dữ liệu gốc và dữ liệu đã khử định danh. Amazon DataZone quản lý governance, kiểm soát truy cập và phân loại để xác minh quản lý dữ liệu và tuân thủ hiệu quả.*

## ***Các bước tiếp theo***

*Hãy chuyển đổi hành trình quản trị dữ liệu của bạn với giải pháp mà chúng tôi vừa trình bày sử dụng tính năng Amazon Bedrock Data Automation.*

*Chúng tôi khuyến nghị trước khi bắt đầu:*

* *Lập bản đồ landscape dữ liệu phi cấu trúc*  
* *Định nghĩa rõ tiêu chí thành công cho nhu cầu của tổ chức bạn*  
* *Bắt đầu pilot tập trung với tài sản dữ liệu giá trị nhất để chứng minh giá trị ngay*  
* *Triển khai rộng toàn tổ chức dựa trên thành công ban đầu*

*Truy cập [GitHub Repository: Guidance for Multimodal Data Processing](https://github.com/aws-solutions-library-samples/guidance-for-multimodal-data-processing-using-amazon-bedrock-data-automation) để bắt đầu ngay hôm nay.*

## ***Kết luận***

 *Khi dữ liệu phi cấu trúc tiếp tục tăng trưởng mạnh mẽ trong mọi ngành, các tổ chức triển khai giải pháp catalog hóa và quản lý hiệu quả sẽ sở hữu lợi thế cạnh tranh lớn. Tính năng Amazon Bedrock Data Automation là một phương pháp mạnh mẽ, dễ mở rộng, có thể biến vấn đề quản lý dữ liệu phi cấu trúc thành tài sản chiến lược khi triển khai.*

 *Dù bạn là tổ chức nghiên cứu hay healthcare, Bedrock Data Automation của chúng tôi giúp bạn phân loại, tìm kiếm và khai thác insight từ dữ liệu phi cấu trúc phức tạp. Giải pháp đảm bảo governance chuẩn và kiểm soát truy cập đúng, đồng thời unlock toàn bộ tiềm năng tài sản dữ liệu.*

 *Liên hệ [AWS Representative](https://pages.awscloud.com/health-contact-us.html) để biết cách chúng tôi có thể giúp tăng tốc doanh nghiệp của bạn.*

## ***Đọc thêm***

* [*Amazon Bedrock Data Automation: Amazon Bedrock Data Automation to transform unstructured data into actionable insights*](https://aws.amazon.com/blogs/machine-learning/unleashing-the-multimodal-power-of-amazon-bedrock-data-automation-to-transform-unstructured-data-into-actionable-insights/)  
* [*AWS Glue Documentation*](https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html)  
* [*Amazon DataZone User Guide*](https://docs.aws.amazon.com/datazone/latest/userguide/what-is-datazone.html)

*![Vani Eswarappa](/images/3-BlogsTranslated/3.3-Blog3/image-1.png)*

### *Vani Eswarappa*

*Vani Eswarappa là Principal Architect tại AWS, có kinh nghiệm về Containers, AI/ML, Enterprise Architecture. Là một technical leader, Vani làm việc với khách hàng AWS về hành trình cloud nhằm đáp ứng nhu cầu kinh doanh. Khi không làm việc, cô thích dành thời gian bên gia đình và khám phá địa điểm mới ngoài trời.*

*![Rupesh Mishra](/images/3-BlogsTranslated/3.3-Blog3/image-2.png)*

### *Rupesh Mishra*

*Rupesh Mishra là Health AI/ML Specialist Solutions Architect tại AWS, với hơn 15 năm kinh nghiệm lâm sàng và kỹ thuật trong ngành healthcare và công nghệ. Anh nỗ lực nâng cao kết quả điều trị thông qua công nghệ và cộng tác cùng khách hàng, đối tác AWS các sáng kiến AI, ML, generative AI. Thời gian rảnh anh thích chơi thể thao, ở bên gia đình, du lịch và khám phá món ăn.*