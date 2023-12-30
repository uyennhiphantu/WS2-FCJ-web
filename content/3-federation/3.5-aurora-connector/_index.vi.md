---
title : "Aurora Connector"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 3.5. </b> "
---

Với Athena Jdbc Connector, các cơ sở dữ liệu sau đã được hỗ trợ:

- MySQL
- PostgreSQL
- Redshift

Để biết thông tin chi tiết về Amazon Athena Jdbc Connector, hãy tham khảo tại đây.

Athena MySql Connector có thể được cài đặt như được nêu bên dưới.

### Cài đặt Athena MySql Connector bằng Athena Console
1. Trong Athena console, nhấp vào biểu tượng bánh hamburger (3 đường ngang) ở góc trên cùng bên trái và chọn "Data sources".
![Alt text](<hinh 1.7.png>)
![Alt text](<hinh 1.8.png>)
2. Ở trang Data Sources, click **Connect data source**
![Alt text](<hinh 1.9.png>)
3. Chọn data source là Mysql mà bạn muốn kết nối, như trong ảnh chụp màn hình sau và click **Next**
![Alt text](<hinh 1.21.png>)
4. Trong phần Data source detail: đối với Data source name, nhập **mysql**.
![Alt text](<hinh 1.22.png>)
5. Lambda function đã được triển khai như một phần của workshop này. Click **Select or enter a Lambda function**. Chọn **mysql** và click 'Next'
![Alt text](<hinh 1.23.png>)
6. Xem lại thông tin và click 'Create data source'
​![Alt text](<hinh 1.24.png>)
7. Click vào Data Source và xác minh rằng new Data Source hiển thị
![Alt text](<hinh 1.25.png>)
8. Click vào mysql datasource và sau đó chọn vào liên kết mysql lambda function như dưới đây:
![Alt text](<hinh 1.26.png>)
9. Điều hướng đến Configuration tab và chọn Environment variables rồi chọn Edit. Thêm một biến new environment variable với tên mysql_connection_string và sao chép giá trị của biến mặc định sang biến mới này (database connection string).
![Alt text](<hinh 1.27.png>)
***Lưu ý: The environment variable name là tên của data source với suffix _connection_string, do đó trong trường hợp này là mysql_connection_string.*** 
![Alt text](<hinh 1.28.png>)
![Alt text](<hinh 1.29.png>)
10. Điều hướng trở lại query editor, chọn nguồn dữ liệu mới và xem xét liệu nó có hiển thị cơ sở dữ liệu hay không. The connector đã được triển khai và sẵn sàng để sử dụng. Bạn có thể gọi connector trong truy vấn của mình là **"lambda:mysql"** hoặc **mysql.sale**
![Alt text](<hinh 1.30.png>)