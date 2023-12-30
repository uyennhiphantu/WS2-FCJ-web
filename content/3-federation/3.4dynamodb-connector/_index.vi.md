---
title : "DynamoDB Connector"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 3.4. </b> "
---

Để biết thông tin chi tiết về Amazon Athena DynamoDB Connector, hãy tham khảo tại đây.

Bạn có thể cài đặt Athena DynamoDB Connector bằng một trong hai cách được nêu bên dưới.
​
### Cài đặt Athena DynamoDB Connector bằng Athena Console
1. Trong bảng điều khiển Athena, nhấp vào biểu tượng bánh hamburger (3 đường ngang) ở góc trên cùng bên trái và chọn "Data sources".
![Alt text](<hinh 1.7.png>)
![Alt text](<hinh 1.8.png>)
2. Trên trang Data sources, click **Connect data source**
![Alt text](<hinh 1.9.png>)
3. Chọn nguồn dữ liệu là DynamoDB mà bạn muốn kết nối, như trong ảnh chụp màn hình sau và click **Next**
![Alt text](<hinh 1.10.png>)
4. Trong Chi tiết nguồn dữ liệu: đối với Data source name, hãy nhập dynamo_db và trong hàm Lambda, click 'Create Lambda function' để mở một tab/cửa sổ mới tới AWS Lambda Console.
![Alt text](<hinh 1.11.png>)
![Alt text](<hinh 1.12.png>)
5. Điền vào các fields cài đặt ứng dụng theo ảnh chụp nhanh bên dưới, click "I acknowledge that this app creates custom IAM roles" và click vào **deploy**:
![Alt text](<hinh 1.13.png>)
![Alt text](<hinh 1.14.png>)  
6. Đợi chức năng triển khai. Quay lại cửa sổ Athena, click nút làm mới bên cạnh Lambda  function. Chọn Lambda function mới được triển khai và nhấp vào 'Next'
![Alt text](<hinh 1.15.png>)
7. Xem lại thông tin và nhấp vào 'Create data source'
![Alt text](<hinh 1.16.png>)
8. Click vào Data Sources và xác minh rằng data source mới hiển thị
![Alt text](<hinh 1.17.png>)
9. Điều hướng trở lại query editor, chọn nguồn dữ liệu mới và xem xét liệu nó có hiển thị cơ sở dữ liệu hay không. Connnector đã được triển khai và sẵn sàng để sử dụng. Bạn có thể gọi connector trong truy vấn của mình là **"lambda:dynamo"** hoặc **dynamo_db.dynamo**
![Alt text](<hinh 1.18.png>)

### Tùy chọn 2: Cài đặt Athena DynamoDB Connector bằng Serverless Application Repository
Để cài đặt Athena DynamoDB Connector, hãy tìm kiếm **"Serverless Application Repository"** trong tài khoản aws của bạn và nhấp vào **"Available applications"**:
![Alt text](<hinh 1.19.png>)
Đảm bảo đánh dấu **"Show apps that create custom IAM roles or resource policies"**. Tìm kiếm **"AthenaDynamoDBConnector"** và chọn thẻ có **AWS verified author**, click vào đó:
​![Alt text](<hinh 1.20.png>)
​Đối với Athena DynamoDB Connector này, có một số trường chúng ta cần hoàn thành:
![Alt text](<hinh 1.13-1.png>)
Click vào "I acknowledge that this app creates custom IAM roles" và click vào **deploy**:
​![Alt text](<hinh 1.14-1.png>)
Thao tác này sẽ triển khai Athena DynamoDB connector và bạn có thể gọi hàm lambda này trong truy vấn của mình là "lambda:dynamo"