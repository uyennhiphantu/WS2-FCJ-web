---
title : "Tạo chế độ xem"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---

Chế độ xem trong Amazon Athena là một bảng logical chứ không phải một bảng physical. Truy vấn xác định chế độ xem sẽ chạy mỗi khi chế độ xem được tham chiếu trong truy vấn. Bạn có thể tạo chế độ xem từ truy vấn SELECT rồi tham chiếu chế độ xem này trong các truy vấn trong tương lai. Để biết thêm thông tin, hãy xem [CREATE VIEW](https://docs.aws.amazon.com/athena/latest/ug/create-view.html)

Bây giờ chúng ta sẽ tạo mới chế độ xem Customer Lifetime Value trong Athena

1. Chọn **Saved Queries** trong Athena Query Editor.
2. Từ danh sách, chọn truy vấn **Athena_create_customer_lifetime_value_view.**
![image](<hinh 33.png>)
3. Có hai phần của truy vấn. Phần đầu tiên là tạo ra chế độ xem the customer lifetime value. Thứ hai là chọn dữ liệu từ chế độ xem.
4. Đánh dấu truy vấn đầu tiên và chọn **Run**. Điều đó sẽ tạo ra một chế độ xem mới có tên là **customer_lifetime_value**
![image](<hinh 34.png>)
5. Khi chế độ xem được tạo, nó sẽ xuất hiện ở **Views** trong trình điều hướng tài nguyên.
![image](<hinh 35.png>)
6. Chọn truy vấn thứ hai và nhấn **RUN** để chọn 10 bản ghi đầu tiên từ chế độ xem.
![image](<hinh 36.png>)
Vậy là bạn đã sử dụng thành công Athena để tạo chế độ xem trong danh mục AWS Glue Data catalog.