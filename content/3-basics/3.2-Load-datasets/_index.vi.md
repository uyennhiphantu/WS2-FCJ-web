---
title : "Tải bộ dữ liệu"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
Trước khi Athena có thể sử dụng được để truy vấn dữ liệu, chúng ta cần phải tải dữ liệu vào nhóm s3.

### Tải dữ liệu vào tài khoản của bạn
Trong thanh điều hướng trên cùng, Chọn biểu tượng cloudshell. 
![image](<hinh 3.png>)

Sau khi tải xong nó sẽ hiển thị như hình dưới đây:
![image](<hinh 4.png>)

Tiếp đến, sao chép và dán phần dưới đây vào terminal
```
accountid=$(aws sts get-caller-identity --query "Account" --output text)
aws s3 cp s3://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee/9981f1a1-abdc-49b5-8387-cb01d238bb78/v1/csv/customers.csv ./customers.csv
aws s3 cp s3://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee/9981f1a1-abdc-49b5-8387-cb01d238bb78/v1/csv/sales.csv ./sales.csv
aws s3 cp customers.csv s3://athena-workshop-$accountid/basics/csv/customers/customers.csv
aws s3 cp sales.csv s3://athena-workshop-$accountid/basics/csv/sales/sales.csv
aws s3 cp s3://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee/9981f1a1-abdc-49b5-8387-cb01d238bb78/v1/parquet/sales.zip ./sales.zip
aws s3 cp s3://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee/9981f1a1-abdc-49b5-8387-cb01d238bb78/v1/parquet/customers.zip ./customers.zip
unzip -o sales.zip
unzip -o customers.zip
aws s3 sync ./sales s3://athena-workshop-$accountid/basics/parquet/sales
aws s3 sync ./customers s3://athena-workshop-$accountid/basics/parquet/customers
echo "----- done -----"
```
{{% notice note %}}
Nếu lời nhắc "Safe Paste for multiline txt" được hiển thị, hãy chọn PASTE
{{% /notice %}}

Sau khi các lệnh xử lý hoàn tất, dữ liệu sẽ được tải vào vùng lưu trữ S3 trong tài khoản của bạn.

Để xác minh dữ liệu đã được tải, hãy làm theo các bước sau:

1. Trong thanh Tìm kiếm ở đầu màn hình, tìm **S3**, sau đó chọn **S3** trong kết quả tìm kiếm
![image](<hinh 5.png>)
2. Xác định vị trí bucket đã được tạo cho workshop. Nó sẽ được đặt tên là **athena-workshop-[số tài khoản AWS của bạn]** ví dụ: 
*athena-workshop-12345678910*
![image](<hinh 6.png>)
3. Chọn bucket name và sau đó kiểm tra:

   1. Có một thư mục tên là **basics**
   2. Thư mục **basics** chứa các thư mục **CSV** và **parquet**

Bây giờ bộ dữ liệu mà chúng ta sẽ sử dụng trong bài lab đã được tải vào tài khoản của bạn.