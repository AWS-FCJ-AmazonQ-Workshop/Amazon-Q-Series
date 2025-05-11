+++
title = "Amazon Q Developer features"
date = 2020-05-14T00:38:32+07:00
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

Amazon Q Developer có sẵn trên khắp các môi trường và dịch vụ AWS, đồng thời cũng là một trợ lý viết mã trong các IDE của bên thứ ba.

Nhiều khả năng của Amazon Q Developer tồn tại trong giao diện trò chuyện, nơi bạn có thể sử dụng ngôn ngữ tự nhiên để đặt câu hỏi về AWS, nhận trợ giúp về mã, khám phá tài nguyên hoặc khắc phục sự cố. Khi bạn trò chuyện với Amazon Q, Amazon Q sử dụng ngữ cảnh của cuộc trò chuyện hiện tại của bạn để đưa ra phản hồi. Bạn có thể đặt câu hỏi tiếp theo hoặc tham khảo phản hồi của nó khi bạn đặt một câu hỏi mới.

Các tính năng khác của Amazon Q Developer có sẵn như một phần của quy trình làm việc của bạn trong bảng điều khiển dịch vụ AWS và các IDE được hỗ trợ. Các phần sau giải thích các tính năng khác nhau của Amazon Q Developer mà bạn có thể gặp phải trong trải nghiệm AWS của mình.

### Di chuyển & Chuyển đổi

#### Trải nghiệm web chuyển đổi Amazon Q Developer

Các khả năng chuyển đổi của Amazon Q Developer có thể giúp doanh nghiệp của bạn khám phá, lập kế hoạch và thực hiện các công việc di chuyển và hiện đại hóa cho các ứng dụng cũ của bạn đang chạy tại chỗ hoặc trên đám mây.

### Phân tích

#### Tóm tắt dữ liệu của bạn

Với Amazon Q Amazon QuickSight, bạn có thể tận dụng trải nghiệm tác giả BI tạo sinh, tạo tóm tắt điều hành về dữ liệu của bạn, đặt và trả lời các câu hỏi về dữ liệu, đồng thời tạo các câu chuyện dữ liệu.

### Quản lý và quản trị

#### Khám phá các nút bằng cách sử dụng lời nhắc văn bản

Sử dụng AWS Systems Manager và Amazon Q, bạn có thể đặt các câu hỏi bằng ngôn ngữ tự nhiên về các nút hoặc phiên bản được quản lý của bạn. Sau đó, Amazon Q sử dụng hành động ListNodes của Systems Manager và tạo các bộ lọc dựa trên đầu vào văn bản của bạn để truy xuất kết quả.

#### Điều tra các vấn đề vận hành (bản xem trước)

Các điều tra vận hành của Amazon Q Developer nâng cao khả năng điều tra và phân tích tài nguyên, sự kiện và hoạt động trên toàn bộ môi trường AWS của bạn. Bằng cách tận dụng xử lý ngôn ngữ tự nhiên, Amazon Q đơn giản hóa quá trình hiểu các kịch bản và mối quan hệ phức tạp trong tài khoản AWS của bạn.

Amazon Q Developer hiện giúp bạn tăng tốc các cuộc điều tra vận hành trên toàn bộ môi trường AWS của bạn. Q tìm kiếm các bất thường trong dữ liệu đo từ xa của bạn, hiển thị các tín hiệu liên quan để bạn khám phá, xác định các giả thuyết về nguyên nhân gốc rễ tiềm ẩn và đề xuất các bước tiếp theo để giúp bạn khắc phục sự cố nhanh hơn.

Bằng cách tích hợp Amazon Q vào quy trình điều tra của bạn, bạn có thể tăng tốc độ giải quyết vấn đề, nâng cao hiểu biết về môi trường AWS của bạn và đưa ra các quyết định sáng suốt hơn về cơ sở hạ tầng và ứng dụng của bạn.

{{% notice note %}}
Tính năng điều tra vận hành của Amazon Q hiện đang ở bản xem trước và có thể thay đổi.
{{% /notice %}}

#### Kiểm kê tài nguyên AWS của bạn

Bạn có thể hỏi Amazon Q về các tài nguyên tài khoản AWS cụ thể của mình từ bất kỳ đâu trong AWS Management Console. Bạn có thể không biết vị trí thông tin liên quan về tài nguyên của mình hoặc bạn có thể đang ở trong một bảng điều khiển dịch vụ và muốn truy cập thông tin về tài nguyên của một dịch vụ khác mà không làm gián đoạn quy trình làm việc của bạn.

Amazon Q Developer trả lời các câu hỏi bằng ngôn ngữ tự nhiên của bạn về tài nguyên và cung cấp các liên kết sâu đến các tài nguyên đó để bạn có thể nhanh chóng tìm thấy chúng. Bạn có thể yêu cầu Amazon Q liệt kê một loại tài nguyên trong tài khoản của bạn, để biết chi tiết về một tài nguyên cụ thể hoặc liệt kê các tài nguyên dựa trên tiêu chí như khu vực hoặc trạng thái.

Ví dụ: bạn có thể muốn biết hiện có bao nhiêu phiên bản Amazon EC2 đang chạy. Trong trường hợp đó, bạn có thể đặt câu hỏi cho Amazon Q bằng ngôn ngữ tự nhiên và nó sẽ cung cấp câu trả lời dựa trên các tài nguyên cụ thể của bạn.

#### Sử dụng Amazon Q trong Ứng dụng Di động AWS Console

Amazon Q được tích hợp với Ứng dụng Di động AWS Console để trả lời các câu hỏi về AWS. Bạn định cấu hình quyền truy cập theo cách tương tự như cách bạn có quyền truy cập vào Amazon Q trong AWS Management Console.

#### Chẩn đoán lỗi bảng điều khiển

Trong AWS Management Console, Amazon Q Developer có thể chẩn đoán các lỗi phổ biến mà bạn gặp phải khi làm việc với các dịch vụ AWS, chẳng hạn như thiếu quyền, cấu hình không chính xác và vượt quá giới hạn dịch vụ.

### Điện toán

#### Lựa chọn các phiên bản Amazon Elastic Compute Cloud

Với rất nhiều loại phiên bản Amazon EC2 có sẵn, việc tìm kiếm các loại phiên bản phù hợp cho khối lượng công việc của bạn có thể tốn thời gian và phức tạp. Công cụ chọn loại phiên bản Amazon Q xem xét trường hợp sử dụng, loại khối lượng công việc, sở thích nhà sản xuất CPU và cách bạn ưu tiên giá cả và hiệu suất, cũng như các tham số bổ sung mà bạn có thể chỉ định. Sau đó, nó sử dụng dữ liệu này để cung cấp các đề xuất và hướng dẫn về các loại phiên bản Amazon EC2 phù hợp nhất với khối lượng công việc mới của bạn.

![ec2-instance-type-finder](/images/1/ec2-instance-type-finder.gif?width=90pc)

### Cơ sở dữ liệu

#### Viết truy vấn cơ sở dữ liệu bằng ngôn ngữ tự nhiên

Amazon Q generative SQL sử dụng AI tạo sinh để phân tích ý định của người dùng, các mẫu truy vấn và siêu dữ liệu lược đồ để xác định các mẫu truy vấn SQL phổ biến trực tiếp trong Amazon Redshift, tăng tốc quá trình tạo truy vấn cho người dùng và giảm thời gian cần thiết để thu được thông tin chi tiết dữ liệu hữu ích.

### Mạng và phân phối nội dung

#### Phân tích khắc phục sự cố mạng

Bạn có thể sử dụng Amazon Q để giúp bạn chẩn đoán các vấn đề về kết nối mạng cho các ứng dụng chạy trong Amazon VPC của bạn. Khả năng khắc phục sự cố mạng của Amazon Q có thể hiểu các truy vấn bằng ngôn ngữ tự nhiên và hoạt động với Reachability Analyzer để cung cấp các phản hồi liên quan. Với Amazon Q, bạn có thể đặt các câu hỏi về khả năng tiếp cận mạng theo định dạng trò chuyện.

### Công cụ dành cho nhà phát triển

Đặt câu hỏi cho Amazon Q Developer về việc xây dựng trên AWS và để được hỗ trợ về phát triển phần mềm. Amazon Q có thể giải thích các khái niệm và đoạn mã, tạo mã và kiểm thử đơn vị, đồng thời cải thiện mã, bao gồm gỡ lỗi hoặc tái cấu trúc.

#### Phát triển các tính năng mã

Sau khi bạn giải thích bằng ngôn ngữ tự nhiên tính năng bạn muốn phát triển, Amazon Q có thể sử dụng ngữ cảnh của dự án hiện tại của bạn để tạo kế hoạch triển khai và mã đi kèm. Amazon Q có thể giúp bạn xây dựng các dự án AWS hoặc các ứng dụng của riêng bạn.

#### Nhận gợi ý mã trực tiếp

Amazon Q cung cấp cho bạn các đề xuất mã theo thời gian thực. Khi bạn viết mã, Amazon Q tự động tạo các gợi ý dựa trên mã và nhận xét hiện có của bạn.

#### Chatting về code trong IDEs

Trong môi trường phát triển tích hợp (IDE), Amazon Q có thể trả lời các câu hỏi liên quan đến quy trình phát triển phần mềm, bao gồm các câu hỏi khái niệm về lập trình và cách hoạt động của mã cụ thể. Bạn cũng có thể yêu cầu Amazon Q cập nhật và cải thiện các đoạn mã từ bảng trò chuyện. Với hỗ trợ đa ngôn ngữ, bạn có thể trò chuyện với Amazon Q bằng bất kỳ ngôn ngữ tự nhiên được hỗ trợ nào, bao gồm tiếng Anh, tiếng Quan Thoại, tiếng Pháp, tiếng Đức, tiếng Ý, tiếng Nhật, tiếng Tây Ban Nha, tiếng Hàn, tiếng Hindi và tiếng Bồ Đào Nha, với nhiều ngôn ngữ khác sẽ được hỗ trợ.

#### Xem xét mã của bạn để tìm các lỗ hổng bảo mật và các vấn đề về chất lượng

Trong IDE, Amazon Q xem xét mã của bạn để tìm các lỗ hổng bảo mật và các vấn đề về chất lượng mã. Amazon Q có thể xem xét khi bạn viết mã hoặc xem xét toàn bộ dự án để theo dõi tính bảo mật và chất lượng của ứng dụng của bạn trong suốt quá trình phát triển.

#### Chuyển đổi mã

Amazon Q có thể thực hiện các nâng cấp tự động về ngôn ngữ và cấp hệ điều hành (OS) cho các ứng dụng của bạn.

#### Tạo kiểm thử đơn vị

Amazon Q Developer cung cấp một tính năng tạo kiểm thử đơn vị được hỗ trợ bởi AI để giúp các nhóm phát triển cải thiện độ bao phủ mã trong suốt vòng đời phát triển phần mềm của họ. Tác nhân Amazon Q Developer để tạo kiểm thử đơn vị có sẵn trong các môi trường sau:

- Tiện ích mở rộng IDE Amazon Q Developer.

- GitLab, như một phần của GitLab Duo.

#### Phát triển phần mềm trong Amazon CodeCatalyst

Amazon Q Developer trong CodeCatalyst bao gồm các tính năng AI tạo sinh có thể giúp người dùng trong các dự án trong không gian của bạn phát triển phần mềm nhanh hơn. Bạn có thể gán vấn đề cho Amazon Q hoặc đề xuất các tác vụ cho Amazon Q. Bạn cũng có thể yêu cầu Amazon Q viết mô tả hoặc tóm tắt nội dung.

#### Trò chuyện về mã trong Amazon SageMaker AI Studio

Amazon SageMaker AI Studio là một trải nghiệm dựa trên web để chạy các quy trình làm việc ML. Bạn có thể trò chuyện với Amazon Q Developer bên trong Studio để được hướng dẫn về các tính năng SageMaker AI, khắc phục sự cố JupyterLab và nhận mã mẫu.

![q-dev-smstudio](/images/1/q-dev-smstudio.png?width=90pc)

#### Tương tác với dòng lệnh và AWS CloudShell

##### Command Line Interface (CLI)

Sau khi cài đặt Amazon Q cho dòng lệnh, bạn có thể sử dụng nó để hoàn thành các lệnh CLI khi nó điền các lệnh con, tùy chọn và đối số phù hợp theo ngữ cảnh. Nó cung cấp các gợi ý hoàn thành do AI tạo ra khi bạn nhập vào dòng lệnh. Ngoài ra, bạn có thể sử dụng Amazon Q để viết các hướng dẫn bằng ngôn ngữ tự nhiên được dịch ngay lập tức thành một đoạn mã shell có thể thực thi. Bạn cũng có thể đặt các câu hỏi phức tạp cho Amazon Q và nó sẽ cung cấp phản hồi và hướng dẫn dựa trên cuộc trò chuyện, cũng như ngữ cảnh và thông tin bên ngoài cuộc trò chuyện. Sau đó, bạn có thể cấp quyền cho Amazon Q để nó thực hiện các hành động thay mặt bạn. Với hỗ trợ đa ngôn ngữ, bạn có thể trò chuyện với Amazon Q bằng bất kỳ ngôn ngữ tự nhiên được hỗ trợ nào, bao gồm tiếng Anh, tiếng Quan Thoại, tiếng Pháp, tiếng Đức, tiếng Ý, tiếng Nhật, tiếng Tây Ban Nha, tiếng Hàn, tiếng Hindi và tiếng Bồ Đào Nha, với nhiều ngôn ngữ khác sẽ được hỗ trợ. French, German, Italian, Japanese, Spanish, Korean, Hindi and Portuguese, with more languages available.

#### AWS CloudShell

Bạn cũng có thể sử dụng Amazon Q CLI trong AWS CloudShell để tương tác trong các cuộc hội thoại bằng ngôn ngữ tự nhiên, đặt câu hỏi và nhận phản hồi từ Amazon Q trong terminal của bạn. Bạn có thể nhận được lệnh shell liên quan giúp giảm nhu cầu tìm kiếm hoặc ghi nhớ cú pháp. Với Amazon Q, bạn có thể nhận được các gợi ý lệnh khi bạn nhập vào terminal.

### Tích hợp ứng dụng

#### Viết script để tự động hóa các dịch vụ AWS

Bạn có thể biết chính xác những gì cần làm với tài nguyên AWS của mình và bạn có thể thấy mình thực hiện đi thực hiện lại cùng một hành động. Trong trường hợp đó, bạn có thể yêu cầu Amazon Q viết mã sẽ tự động hóa các tác vụ lặp đi lặp lại.

Ví dụ: bạn có thể đang làm việc trên một dự án sử dụng Amazon VPC, các phiên bản Amazon EC2 và cơ sở dữ liệu Amazon RDS. Trong quá trình thử nghiệm, bạn thấy rằng mỗi khi bạn tạo Amazon VPC, khởi chạy một máy chủ và triển khai cơ sở dữ liệu, cấu hình đều giống nhau. Bạn luôn chọn cùng một loại phiên bản và cơ sở dữ liệu, với cùng các tùy chọn được chọn, sử dụng cùng các nhóm bảo mật, trong các subnet có cùng cấu hình NACL. Bạn không muốn phải trải qua cùng một quy trình thủ công mỗi khi bạn muốn tạo lại các điều kiện thử nghiệm của mình.

Bạn có thể sử dụng tính năng Console-to-Code của Amazon Q để tự động hóa quy trình làm việc thay vì thực hiện thủ công mỗi lần. Đầu tiên, bạn kích hoạt Console-to-Code trong bảng điều khiển Amazon EC2. Sau đó, Amazon Q ghi lại các hành động của bạn khi bạn thực hiện quy trình định cấu hình và khởi chạy phiên bản của mình. Cuối cùng, Amazon Q cung cấp cho bạn mã, bằng ngôn ngữ bạn chọn, để tự động hóa quy trình bạn vừa thực hiện.

#### Viết script ETL và tích hợp dữ liệu

AWS Glue là một dịch vụ tích hợp dữ liệu không máy chủ, giúp người dùng phân tích dễ dàng khám phá, chuẩn bị, di chuyển và tích hợp dữ liệu từ nhiều nguồn khác nhau.

Tích hợp dữ liệu Amazon Q trong AWS Glue bao gồm các khả năng sau:

- **Trò chuyện** – Tích hợp dữ liệu Amazon Q trong AWS Glue có thể trả lời các câu hỏi bằng ngôn ngữ tự nhiên (tiếng Anh) về AWS Glue và các lĩnh vực tích hợp dữ liệu như các trình kết nối nguồn và đích AWS Glue, các công việc ETL AWS Glue, Data Catalog, trình thu thập dữ liệu và AWS Lake Formation, cũng như các tài liệu và phương pháp hay nhất khác về tính năng. Tích hợp dữ liệu Amazon Q trong AWS Glue phản hồi bằng các hướng dẫn từng bước và bao gồm các tham chiếu đến các nguồn thông tin của nó.

- **Tạo mã tích hợp dữ liệu** – Tích hợp dữ liệu Amazon Q trong AWS Glue có thể trả lời các câu hỏi về các script ETL AWS Glue và tạo mã mới dựa trên câu hỏi bằng ngôn ngữ tự nhiên (tiếng Anh).

- **Khắc phục sự cố** – Tích hợp dữ liệu Amazon Q trong AWS Glue được xây dựng có mục đích để giúp bạn hiểu các lỗi trong các công việc AWS Glue và cung cấp các hướng dẫn từng bước để xác định nguyên nhân và giải quyết các vấn đề của bạn.

### Công cụ của bên thứ ba

#### Sử dụng GitLab Duo với Amazon Q

Bạn có thể [sử dụng GitLab Duo với Amazon Q](https://docs.gitlab.com/ee/user/duo_amazon_q/) cho các hoạt động phát triển phần mềm và quy trình quản lý mã nguồn của mình. Sau khi thiết lập Amazon Q trong GitLab Duo, bạn có thể gọi [các hành động nhanh](https://docs.gitlab.com/ee/user/project/quick_actions.html) để tự động hóa các tác vụ.

### Quản lý Tài chính Đám mây

#### Understanding your costs

Bạn có thể hỏi Amazon Q về hóa đơn AWS và chi phí tài khoản của mình trong AWS Management Console. Amazon Q có thể truy xuất dữ liệu chi phí của bạn, giải thích chi phí và phân tích xu hướng chi phí.

### Hỗ trợ khách hàng

#### Nhận hỗ trợ khách hàng trực tiếp từ Amazon Q

Amazon Q có thể trả lời các câu hỏi của bạn về kích hoạt tài khoản, tăng đột biến chi phí, điều chỉnh hóa đơn, các sự kiện gian lận, các sự kiện về tình trạng hoạt động và các vấn đề với tài nguyên AWS của bạn.

#### Tạo phiếu hỗ trợ

Amazon Q có thể giúp bạn tạo một trường hợp hỗ trợ và sau đó kết nối bạn với một nhân viên hỗ trợ thực tế tại AWS.

#### Amazon Q trong các ứng dụng trò chuyện

Bạn có thể kích hoạt Amazon Q trong các ứng dụng Slack và Microsoft Teams của mình để đặt câu hỏi về việc xây dựng trên AWS.
