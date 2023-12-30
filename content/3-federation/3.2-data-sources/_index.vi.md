---
title : "Data Sources"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
Giả định một công ty thương mại điện tử có kiến ​​trúc sử dụng như sau:

- Xử lý bản ghi Lineitems được lưu trữ trong **HBase trên EMR**
- Sử dụng **Redis** để lưu trữ thông tin về quốc gia và các đơn hàng hoạt động để hệ thống xử lý có thể truy cập nhanh chóng vào chúng
- Aurora với động cơ MySQL để lưu trữ dữ liệu về Orders, Customer và Suppliers  như địa chỉ email, địa chỉ giao hàng, vv.
- Sử dụng **DynamoDB** để lưu trữ dữ liệu về các part và partsupp data để đạt hiệu suất cao.
![Alt text](image.png)
![Alt text](image-1.png)

Đối với workshop này, chúng ta sẽ tập trung vào các nguồn dữ liệu sau:
### HBase trên EMR
- Hệ thống lưu trữ dữ liệu tối ưu
- Tỷ lệ giao dịch cao
- Độ bền lâu dài **Aurora với MySQL engine**
- Bản sao đọc có thể mở rộng
- Có khả năng mở rộng đọc bản sao
- Yêu cầu tỷ lệ ghi thấp
- Bảo mật cao **Amazon DynamoDB**
- Có khả năng mở rộng cao
- Hiệu suất cao
- Linh hoạt **Redis trên ElastiCache**
- Đọc và ghi với độ trễ thấp
- Ít thông tin ngữ cảnh
- Trong bộ nhớ với khả năng tái tạo