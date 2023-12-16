---
title : "Tạo bảng"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

### Athena kích hoạt Cloudwatch Metrics

Trước tiên, hãy bật Cloudwatch Metrics cho **primary** Athena workgroup, qua đó chúng ta có thể xem các metrics sau khi chạy truy vấn trong workshop này.

1. Từ các dịch vụ ở menu, tìm kiếm Athena và đi tới bảng điều khiển: 
![image](<hinh 7.png>)
2. Trong bảng điều khiển Athena, chọn biểu tượng bánh hamburger (3 đường ngang) ở góc trên cùng bên trái và chọn **Workgroups** rồi chọn **primary** workgroup.
![image](<hinh 8.png>)
3. Chọn **Edit**
![image](<hinh 9.png>)
4. Cuộn xuống mục Settings, chọn tính năng **Publish query metrics to AWS CloudWatch** và chọn tiếp **Save changes**
![image](<hinh 10.png>)

### Athena Interface - Thiết lập Athena results location

Trong bảng điều khiển Athena, chọn biểu tượng bánh hamburger (3 đường ngang) ở góc trên cùng bên trái và chọn **Query editor**.

5. Chọn **Settings** và sau đó chọn **Manage**
![image](<hinh 11.png>)
6. Trong Manage Settings, chọn **Browse S3**
![image](<hinh 12.png>)
7. Tìm bucket có tên: **athena-workshop-<<id tài khoản>>** ví dụ: athena-workshop-12345678910. Nhấn vào nút radio ở bên trái tên nhóm rồi chọn **Choose**.
![image](<hinh 13.png>)
8. Bấm **Save** để lưu vị trí S3
![image](<hinh 14.png>)

### Athena Interface -  Tạo Bảng và Chạy Truy Vấn

Ngay sau đây, chúng ta sẽ tạo một số bảng mới và chạy truy vấn cho nó.

9. Chọn **Editor** tab để hiển thị trình soạn thảo truy vấn Athena.
10. Đảm bảo bạn đang ở trong **default** database trước khi bắt đầu chạy truy vấn. Kiểm tra xem danh sách thả xuống ở Database có hiển thị default không.
![image](<hinh 15.png>)
Nếu bạn không thấy **default** database, hãy sao chép truy vấn bên dưới, vào mục editor truy vấn và chọn Run:
``
CREATE database default
``
11. Ở bước này chúng ta sẽ tạo 4 bảng mới:

  1. customer_csv
  2. sales_csv
  3. customer_parquet
  4. sales_parquet

Để tiết kiệm thời gian chúng ta sẽ sử dụng các truy vấn đã lưu.

**Tạo bảng customer_csv:**

1. Chọn **Saved queries** tab 
2. Chọn ID truy vấn cho truy vấn có tên: **Athena_create_customers_csv** để mở truy vấn
![image](<hinh 16.png>)
3. Chọn **Run**
4. Kiểm tra tab kết quả truy vấn để đảm bảo nó hiển thị là **Completed**
![image](<hinh 17.png>)

**Tạo bảng sales_csv:**
1. Chọn **Saved queries** tab 
2. Chọn ID truy vấn cho truy vấn có tên: **Athena_create_sale_csv** để mở truy vấn
3. Chọn **Run**
4. Kiểm tra tab kết quả truy vấn để đảm bảo nó hiển thị là **Completed**

**Tạo bảng customer_parquet:**
1. Chọn **Saved queries** tab 
2. Chọn ID truy vấn cho truy vấn có tên: **Athena_create_customers_parquet** để mở truy vấn
3. Đánh dấu truy vấn CREATE TABLE
![image](<hinh 18.png>)
4. Chọn **Run** 
5. Kiểm tra tab kết quả truy vấn để đảm bảo nó hiển thị là **Completed**
6. Chọn dòng chữ **MSCK REPAIR TABLE customer_parquet** và chọn RUN để thêm phân vùng
7. Sau khi hoàn tất, chọn dòng chữ **SHOW PARTITIONS sales_parquet** và chọn RUN

**Tạo bảng sales_parquet:**
1. Chọn **Saved queries** tab  
2. Chọn ID truy vấn cho truy vấn có tên: **Athena_create_sale_parquet** để mở truy vấn
3. Đánh dấu truy vấn CREATE TABLE
4. Chọn **Run**
5. Kiểm tra tab kết quả truy vấn để đảm bảo nó hiển thị là **Completed**
6. Chọn dòng chữ: **MSCK REPAIR TABLE sales_parquet** và chọn run để thêm partitions
7. Sau khi hoàn tất, chọn dòng chữ **HOW PARTITIONS sales_parquet** và chọn RUN

##  Phân vùng dữ liệu trong Athena

Bằng cách phân vùng dữ liệu, chúng ta có thể hạn chế lượng dữ liệu được quét bởi mỗi truy vấn, từ đó cải thiện hiệu suất và giảm chi phí. Bạn có thể phân vùng dữ liệu của mình bằng bất kỳ khoá nào. Một thực tế khá phổ biến là phân vùng dữ liệu dựa trên ngày hoặc giờ, nên thường dẫn đến giải pháp phân vùng đa cấp (Multi-level partitioning scheme).

Athena có thể sử dụng các phân vùng kiểu Apache Hive, có đường dẫn dữ liệu chứa các cặp giá trị khóa được kết nối với nhau bằng dấu “=" (ví dụ: country=us/... hoặc Year=2021/month=01/day=26/...). Do đó, các đường dẫn bao gồm cả tên của các khóa phân vùng và các giá trị mà mỗi đường dẫn đại diện. Để tải các phân vùng Hive mới vào một bảng được phân vùng, chúng ta có thể sử dụng lệnh MSCK REPAIR TABLE, và lệnh này chỉ hoạt động với các phân vùng kiểu Hive.

Athena cũng có thể sử dụng các sơ đồ phân vùng kiểu non-Hive. Ví dụ: nhật ký CloudTrail và luồng phân phối Kinesis Data Firehose sử dụng các thành phần đường dẫn riêng biệt cho các phần ngày như data/2021/01/26/us/6fc7845e.json. Đối với dữ liệu non-Hive, bạn nên sử dụng ALTER TABLE ADD PARTITION để thêm các phân vùng theo cách thủ công.

### So sánh hiệu suất giữa các bảng

Ở phần phía trên, chúng ta đã tạo xong các bảng, nên chúng ta sẽ chạy một số truy vấn để kiểm tra hiệu suất giữa các bảng:

1. Chọn **Saved Queries** tab 
2. Chọn ID truy vấn cho truy vấn có tên: **Athena_Compare_Sales** để mở truy vấn
![Alt text](<hinh 19.png>)
Chạy các truy vấn theo thứ tự bằng cách chọn SQL statement block mỗi lần và nhấp vào nút RUN. Trong phần Query Results, hãy lưu ý các giá trị Run Time và Data Scanned.
![image](<hinh 20-1.png>)
Bạn sẽ thấy rằng khi truy vấn tệp parquet, số lượng Data Scanned ít hơn so với khi truy vấn tệp CSV. Lưu ý rằng Time Taken giữa tệp CSV và tệp parquet là tương tự nhau. Điều này xảy ra bởi vì chúng ta đang sử dụng các tập dữ liệu nhỏ cho bài lab. Khi làm việc với các tập tin có nhiều cột và hàng, parquet nhìn chung sẽ nhanh hơn.