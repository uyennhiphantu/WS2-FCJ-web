---
title : "Amazon Athena là gì?"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1.1 </b> "
---

Amazon Athena là một dịch vụ truy vấn giúp dễ dàng tương tác và phân tích dữ liệu một cách hiệu quả trong Amazon S3 bằng cách sử dụng SQL tiêu chuẩn (ANSI SQL). Chúng ta không cần thực hiện thao tác Trích xuất-Chuyển đổi-Tải (ETL) để nhập dữ liệu vào Athena. Thay vào đó, xác định các lược đồ trỏ đến dữ liệu nằm trong Amazon S3 và để ngay lập tức bắt đầu đưa ra truy vấn cũng như nhận thông tin chuyên sâu. Athena không có máy chủ nên không có cơ sở hạ tầng để thiết lập, cung cấp hoặc quản lý nên bạn sẽ chỉ trả tiền cho những truy vấn mà bạn chạy.

Điều này cho phép bất kỳ ai có kiến thức về SQL có thể nhanh chóng đánh giá các tập dữ liệu quy mô lớn. Athena được tích hợp sẵn với AWS Glue Data Catalog, cho phép bạn xây dựng kho lưu trữ siêu dữ liệu chung trên nhiều dịch vụ, thu thập thông tin nguồn dữ liệu để định vị schema, và cập nhật Catalog của bạn với các định nghĩa về modified table và partition, đồng thời duy trì phiên bản schema.

### Start Querying Instantly

Amazon Athena là một hệ thống không có máy chủ, bạn có thể nhanh chóng truy vấn dữ liệu của mình mà không cần phải thiết lập và quản lý bất kỳ máy chủ hoặc kho dữ liệu nào. Chỉ cần trỏ tới dữ liệu của bạn trong Amazon S3, xác định schema và bắt đầu truy vấn bằng trình chỉnh sửa truy vấn tích hợp sẵn. Amazon Athena cho phép bạn khai thác tất cả dữ liệu của mình trong S3 mà không cần thiết lập các quy trình phức tạp để trích xuất, chuyển đổi và tải dữ liệu (ETL).

### Pay Per Query

Bạn chỉ trả tiền cho dữ liệu được quét (data scanned) bởi Amazon Athena cũng như những truy vấn mà bạn chạy. Với mỗi terabyte mà bạn truy vấn, bạn sẽ bị tính phí là 5$. Bạn có thể tiết kiệm từ 30% đến 90% chi phí cho mỗi truy vấn và đạt được hiệu suất tốt hơn bằng cách nén, phân vùng và chuyển đổi dữ liệu của mình thành định dạng cột. Athena truy vấn dữ liệu trực tiếp trên Amazon S3. Không có phí lưu trữ bổ sung ngoài S3.

### Open, Powerful, Standard

Amazon Athena được xây dựng trên cơ sở của Presto và sử dụng Presto kết hợp với hỗ trợ cho ANSI SQL. Nó có khả năng hoạt động với nhiều định dạng dữ liệu chuẩn như CSV, JSON, ORC, Avro và Parquet. Athena được thiết kế đặc biệt để truy vấn nhanh chóng hoặc truy vấn đơn (ad-hoc query), bên cạnh đó nó cũng có khả năng xử lý phân tích phức tạp, bao gồm các large joins, window functions và cấu trúc dữ liệu mảng (arrays). Amazon Athena luôn sẵn sàng hỗ trợ và thực hiện các truy vấn bằng cách sử dụng tài nguyên tính toán trên nhiều cơ sở và thiết bị trong từng cơ sở. Nó lưu trữ dữ liệu cơ bản trên Amazon S3, đảm bảo tính sẵn có và bền bỉ của dữ liệu.

### Fast, Really Fast

Hiệu suất tương tác cao ngay cả đối với các tập dữ liệu lớn. Với Amazon Athena, bạn không cần phải lo lắng về việc có đủ tài nguyên điện toán hay nó có được hiệu suất truy vấn tương tác nhanh chóng hay không. Bởi vì Amazon Athena tự động thực hiện các truy vấn song song nên hầu hết kết quả đều được trả về trong vòng vài giây.