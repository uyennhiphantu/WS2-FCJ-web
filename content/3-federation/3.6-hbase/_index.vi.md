---
title : "HBase Connector"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 3.6. </b> "
---
---

Để biết thông tin chi tiết về Amazon Athena HBase Connector, hãy tham khảo tại đây.

Athena HBase Connector có thể được cài đặt như được nêu dưới đây.

### Cài đặt Athena HBase Connector bằng Athena Console
1. Trong bảng điều khiển Athena, nhấp vào biểu tượng bánh hamburger (3 đường ngang) ở góc trên cùng bên trái và chọn "Data sources".
![Alt text](<hinh 1.7.png>)
![Alt text](<hinh 1.8.png>)
2. Trên trang Data Sources, nhấp vào **Connect data source** 
![Alt text](<hinh 1.9.png>)
3. Chọn data source là Apache HBase mà bạn muốn kết nối, như trong ảnh chụp màn hình sau và nhấp vào **Next**
![Alt text](<hinh 1.31.png>)
4. Trong phần chi tiết Data source: phần Data source name, nhập **hbase_db**.
![Alt text](<hinh 1.32.png>)
5. Lambda function đã được triển khai như một phần của workshop này. Click vào **Select or enter a Lambda function**. Chọn **hbase** và nhấp vào 'Tiếp theo'
![Alt text](<hinh 1.33.png>)
6. Xem lại thông tin và nhấp vào 'Create data source'
![Alt text](<hinh 1.34.png>)
7. Click vào Data Sources và xác minh rằng new data source hiển thị
![Alt text](<hinh 1.35.png>)
8. Điều hướng trở lại query editor và chọn nguồn dữ liệu mới và xem xét liệu nó có hiển thị cơ sở dữ liệu hay không. Connector đã được triển khai và sẵn sàng để sử dụng. Bạn có thể xem xét connector trong truy vấn của mình dưới dạng **"lambda:hbase"** hoặc **hbase_db.hbase**.
![Alt text](<hinh 1.36.png>)