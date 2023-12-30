---
title : "Các bước chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

### Labs - Federated Queries, User Defined Functions

  
{{% notice note %}}
CloudFormation stack sẽ mất khoảng 20-30 phút để hoàn thành.
{{% /notice %}}

#### **[Launch stack](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=athena-federation-workshop&templateURL=https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/9981f1a1-abdc-49b5-8387-cb01d238bb78/v1/CloudFormation/Athena-Federation-Workshop.yaml)**

{{% notice note %}}
CloudFormation stack sẽ mất khoảng 20-30 phút để hoàn thành.
{{% /notice %}}

CloudFormation stack sẽ tạo một cơ sở dữ liệu TPC mẫu chạy trên Amazon RDS, Amazon EMR Cluster với HBase, Amazon Elasticache Redis, Amazon DynamoDB, Glue Database và tables, S3 Bucket, S3 VPC Endpoint, Glue VPC Endpoint, Athena Named Queries, Cloud9 IDE, phiên bản SageMaker Notebook và các tài nguyên IAM khác. Kiểm tra bảng điều khiển CloudFormation và đợi trạng thái **CREATE_COMPLETE** như hiển thị bên dưới:
![Alt text](<hinh 1.1.png>)
Khi bạn thấy CloudFormation đã hoàn tất, hãy truy cập EMR console và kiểm tra trạng thái của các bước. Đợi nếu nó ở trạng thái Running để nó hoàn thành.

Để khởi chạy EMR, hãy truy cập Dịch vụ và nhập EMR như hiển thị ở đây:
![Alt text](<hinh 1.2.png>)
Sau khi khởi chạy EMR, bạn sẽ thấy nó được hiển thị như thế này:
![Alt text](<hinh 1.3.png>)
Click vào **EMR-Hbase-Cluster**.

Sau đó click Steps như hình bên dưới để kiểm tra trạng thái của bước đó. Đợi cho đến khi nó hiển thị hoàn thành.
![Alt text](<hinh 1.4.png>)

Sau khi quá trình tạo stack hoàn tất, tài khoản AWS của bạn sẽ có tất cả tài nguyên cần thiết để chạy workshop này. Ghi lại tên S3 lake bucket name, subnets, WorkshopSecurityGroup, EMRSecurityGroup, HbaseConnectionString, RDSConnectionString từ tab đầu ra và chuyển sang chương tiếp theo để chạy lab khác.
​![Alt text](<hình 1.5.png>)