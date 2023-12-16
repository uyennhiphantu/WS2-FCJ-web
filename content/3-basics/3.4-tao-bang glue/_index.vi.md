---
title : "Tạo bảng với Glue"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 3.4. </b> "
---

Trong bài lab này, chúng ta sẽ sử dụng Glue Crawler để thu thập dữ liệu về sales và tạo bảng mới trong AWS Glue Data Catalog. Sau đó chúng ta sẽ sử dụng Athena để truy vấn bảng đó.

1. Ở thanh tìm kiếm đầu màn hình tìm :**Glue** sau đó chọn **AWS Glue** từ kết quả tìm kiếm để mở bảng điều khiển AWS Glue.
![image](<hinh 21.png>)
2. Trong bảng điều khiển AWS Glue, hãy chọn **Crawlers** từ bảng chọn bên trái. Sau đó chọn **Create Crawler**
![image](<hinh 22.png>)
3. Nhập **Athena Sales** ở mục Name và chọn Next
![image](<hinh 23.png>)
4. Chọn **Not yet** cho câu hỏi "Is your data already mapped to Glue tables?”. Sau đó chọn tiếp **Add a Data Source**
![Alt text](<hinh 24.png>)
5. Đảm bảo rằng danh sách cuộn xuống của Data Source đã chọn S3. Trong file Path S3, chọn **Browse S3** sau đó:

  1. Chọn nhóm bắt đầu bằng **athena-workshop-**
  2. Chọn thư mục **Basics**, sau đó chọn tiếp vào thư mục **parquet**
  3. Nhấn vào vòng tròn bên trái thư mục **sales**
  4. Chọn **Choose**

Giữ nguyên các cài đặt khác và nhấn vào **Add an S3 Data source**
![image](<hinh 25.png>)
6. Chọn **Next**
![image](<hinh 26.png>)
7. Chọn **Create new IAM Role,** Nhận **AWSGlueServiceRole-salescrawler** làm tên vai trò và chọn **Create**
![image](<hinh 27.png>)
8.  Chọn **Next**
9. Ở màn hình **Set output and scheduling,** chúng ta sẽ thiết lập như sau:
- **Target Database:** default
- **Table Name Prefix - optional:** athena_glue_
Để nguyên các cài đặt khác và chọn **Next**
![image](<hinh 28.png>)
10. Trên màn hình hiển thị **Review and Create**, chọn **Create Crawler**
11. Khi crawler được tạo, hãy nhấp vào **Run crawler**. Có thể mất 2-4 phút để crawler hoàn thành.
![image](<hinh 29.png>)
12. Sau khi crawler hoàn tất, bạn sẽ thấy 1 bảng được thêm vào.
![image](<hinh 30.png>)

### Truy vấn bảng mới với Athena
Bây giờ chúng ta sẽ quay lại Bảng điều khiển Athena và sau đó chạy truy vấn.

1. Trong thanh tìm kiếm phía trên màn hình tìm: **Athena**. Chọn **Athena** từ kết quả tìm kiếm để mở bảng điều khiển Athena
2. Ở phía bên trái của query editor, bạn sẽ thấy bảng **athena_glue_sales** trong danh sách Tables. Chọn biểu tượng dấu ba chấm (3 dấu chấm) bên phải tên bảng rồi chọn **Preview Table**
![image](<hinh 31.png>)
3. Truy vấn sẽ chạy và trả về dữ liệu sales.
![image](<hinh 32.png>)

Vậy là bạn đã tạo thành công một bảng mới bằng cách sử dụng AWS Glue Crawler.

