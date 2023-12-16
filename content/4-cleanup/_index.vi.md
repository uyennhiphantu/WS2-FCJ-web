+++
title = "Dọn dẹp tài nguyên  "
date = 2021
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

Chúng ta sẽ tiến hành các bước sau để xóa các tài nguyên chúng ta đã tạo trong bài thực hành này.

#### Xóa S3 bucket

1. Truy cập [giao diện quản trị dịch vụ S3](https://s3.console.aws.amazon.com/s3/home?region=us-east-1). Chúng ta sẽ thấy S3 bucket được tạo ra từ Cloudformation là athena-workshop-
![Alt text](<hinh 74.png>)
2. Đầu tiên, đảm bảo rằng S3 bucket đã được làm sạch data bằng cách nhấn vào  Empty.
![Alt text](<hinh 75.png>)
3. Nhập *permanently delete* vào ô để xác nhận làm sạch dữ liệu. Sau đó chọn Empty. 
![Alt text](<hinh 76.png>)
4. Quay lại danh sách S3 bucket, chọn athena-workshop-, sau đó nhấn Delete
![Alt text](<hinh 77.png>)
5. Tiếp đó, nhập tên của S3 bucket *athena-workshop-*, rồi chọn Delete.
![Alt text](<hinh 78.png>)

#### Xóa Cloudformation
1. Truy cập [giao diện quản trị dịch vụ Cloudformation](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringText=&filteringStatus=active&viewNested=true). Sau đó chúng ta sẽ thấy mục stack đã tạo 
![Alt text](<hinh 73.png>)
2. 