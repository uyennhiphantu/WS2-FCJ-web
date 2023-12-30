---
title : "Cài đặt Development Environment"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.2. </b> "
---
**Sao chép SDK và chuẩn bị môi trường phát triển của bạn.** Trước khi bắt đầu, hãy đảm bảo rằng git đã được cài đặt trên hệ thống của bạn bằng lệnh sau.
```
sudo yum install git -y 
```
**Cài đặt AWS Query Federation SDK**
Nhập thông tin sau vào dòng lệnh để sao chép kho SDK. Kho lưu trữ này bao gồm SDK, ví dụ và bộ trình kết nối nguồn dữ liệu. Để biết thêm thông tin về trình kết nối nguồn dữ liệu, hãy xem  **Using Amazon Athena Federated Query**.
```
git clone https://github.com/awslabs/aws-athena-query-federation.git 
```
**Install prerequisites** Nếu bạn đang làm việc trên máy phát triển đã cài đặt sẵn Apache Maven, AWS CLI và công cụ xây dựng AWS Serverless Application Model, bạn có thể bỏ qua bước này. Từ thư mục gốc của thư mục aws-athena-query-federation mà bạn đã tạo khi sao chép, hãy chạy tập lệnh prepare_dev_env.sh để chuẩn bị cho môi trường phát triển của bạn.

```
cd aws-athena-query-federation
sudo chown ec2-user:ec2-user ~/.profile
curl https://aws-data-analytics-workshops.s3.amazonaws.com/athena-workshop/scripts/prepare_dev_env.sh > tools/prepare_dev_env.sh
curl https://aws-data-analytics-workshops.s3.amazonaws.com/athena-workshop/scripts/publish.sh > tools/publish.sh

./tools/prepare_dev_env.sh
```

Cập nhật shell của bạn để lấy nguồn các biến mới được tạo bởi quá trình cài đặt hoặc khởi động lại phiên cuối của bạn.

```
source ~/.profile
```