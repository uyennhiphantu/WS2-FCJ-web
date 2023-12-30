---
title : "Truy vấn bằng UDF"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

Bây giờ UDF Connector code đã được triển khai, chúng ta có thể chạy các truy vấn sử dụng UDF:

- Tìm kiếm Athena trong Services như hiển thị bên dưới:
![Alt text](image.png)
- Đảm bảo bạn đang ở trong Workgroup: **V2EngineWorkGroup**. Nếu không nhấn vào Workgroup rồi chọn V2EngineWorkGroup và click **Switch Workgroup**
![Alt text](image-1.png)
- Nhấp vào Saved Queries và chọn **RedactUdfCustomerAddress**
![Alt text](image-2.png)
Bạn sẽ thấy nó như thế này:
![Alt text](image-3.png)
Để tìm hiểu thêm về cú pháp UDF bấm vào đây:  UDF Query Syntax 
Click **Run query**. Khi truy vấn thực hiện thành công, bạn sẽ thấy kết quả như thế này:
![Alt text](image-4.png)