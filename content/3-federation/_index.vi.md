---
title : "Athena Federation"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

### Truy vấn dữ liệu mọi nơi

Chạy các federated queries đối với databases, data warehouses, object stores, và non-relational data stores. Truy vấn Federated SQL cho phép chúng ta truy vấn dữ liệu được thiết lập từ bất kỳ nơi nào có dữ liệu đó. Chúng ta có thể sử dụng dữ liệu SQL thường dùng để JOIN trên nhiều nguồn dữ liệu để phân tích nhanh chóng, và lưu trữ kết quả trong Amazon S3 để sử dụng sau này. Truy vấn Athena federated cũng đưa ra truy vấn Federation SDK mới cho phép chúng ta viết trình kết nối nguồn dữ liệu của riêng mình để truy vấn các kho dữ liệu tùy chỉnh.

![Alt text](image-1.png)

### Federated Queries Labs!
Amazon Athena sử dụng các nguồn dữ liệu chạy trên AWS Lambda để thực hiện các truy vấn federated. Một trình kết nối dữ liệu là một đoạn mã có thể chuyển giữa nguồn dữ liệu mục tiêu của chúng ta và Athena. Bạn có thể coi trình kết nối dữ liệu như một phần mở rộng của công cụ truy vấn của Athena. Khi một truy vấn được gửi đến một nguồn dữ liệu, Athena gọi trình kết nối dữ liệu tương ứng để xác định các phần của các bảng cần đọc, quản lý tính song song và đẩy các điều kiện lọc xuống. Dựa trên việc người dùng gửi truy vấn, các trình kết nối dữ liệu có thể cung cấp hoặc hạn chế truy cập vào các phần dữ liệu cụ thể. Bằng cách thực hiện các bài tập từ những bài thực hành này, chúng ta sẽ biết cách sử dụng các trình kết nối  dữ liệu Amazon Athena khác nhau để chạy các truy vấn federated. Kinh nghiệm với Amazon Athena sẽ hữu ích nhưng không bắt buộc. Hãy làm theo các bước sau một cách tuần tự để hoàn thành các bài thực hành sau:

### Nội dung
- 3.1 [TPCH Database & Tables](3.1-tpch)
- 3.2 [Data Sources](3.2-data-sources)
- 3.3 [Prerequisites](3.3-prerequisites)
- 3.4 [DynamoDB Connector](3.4dynamodb-connector)
- 3.5 [Aurora Connector](3.5-aurora-connector)
- 3.6 [HBase Connector](3.6-hbase)
- 3.7 [Redis Connector](3.7-redis-connector)
- 3.8 [Run Federated Queries](3.8-run-federated)
- 3.9 [Visualize with QuickSight](3.9-visual)


