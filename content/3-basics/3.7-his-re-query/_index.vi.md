---
title : "Kết quả và lịch sử truy vấn"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 3.7. </b> "
---
---

Amazon Athena tự động lưu trữ kết quả truy vấn và thông tin siêu dữ liệu cho mỗi truy vấn chạy ở trong kết quả truy vấn mà bạn có thể chỉ định trong Amazon S3. Nếu cần, bạn có thể truy cập vào các tệp ở đây để làm việc với chúng. Bạn cũng có thể tải xuống tệp kết quả truy vấn trực tiếp từ bảng điều khiển Athena.

1. Để xem lịch sử truy vấn, nhấp vào **Recent queries**. Chúng ta sẽ có thể xem tất cả các truy vấn được gửi trong workgroup, State, Run Time và Data scanned. Chúng ta cũng có thể chọn ID truy vấn và nhấp vào Download results để tải xuống dưới dạng dữ liệu csv.
![image](<hinh 48.png>)
2. Thông tin chi tiết về từng truy vấn chạy cũng được lưu vào Athena results bucket của chúng ta. Trong thanh tìm kiếm ở đầu màn hình tìm **S3** và nhấp vào **S3** trong kết quả tìm kiếm
![image](<hinh 49.png>)
3. Xác định vị trí bucket đã được tạo cho workshop. Nó sẽ được đặt tên là **athena-workshop-[số tài khoản AWS của bạn]** ví dụ: *athena-workshop-12345678910.* Nhấp vào tên bucket để mở nó.
4. Có một prefix cho mỗi Saved Query đã được chạy và một thư mục Unsaved. Thư mục Unsaved lưu trữ kết quả của các truy vấn unsaved được thực hiện từ bảng điều khiển Athena. **Lưu ý:** *Nếu không thấy thư mục Unsaved, bạn có thể sao chép một trong các truy vấn trước đó vào Query tab mới trong Athena, chạy truy vấn đó rồi kiểm tra lại trong S3 bucket.*
![image](<hinh 50.png>)
5.  Nhấp vào **Athena_compare_sale** prefix, sau đó nhấp vào prefix Year,prefix Month và prefix Day.
6. Bạn sẽ thấy kết quả được lưu trữ với id truy vấn.
![image](<hinh 51.png>)