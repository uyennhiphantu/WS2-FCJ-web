---
title : "Redis Connector"
date :  "`r Sys.Date()`" 
weight : 7 
chapter : false
pre : " <b> 3.7. </b> "
---
---

Để biết thông tin chi tiết về Amazon Athena Redis Connector, hãy tham khảo tại đây.

Athena Redis Connector có thể được cài đặt như được nêu bên dưới.

### Cài đặt Athena Redis Connector bằng Bảng điều khiển Athena
1. Trong Athena Console, nhấp vào biểu tượng bánh hamburger (3 đường ngang) ở góc trên cùng bên trái và chọn "Data sources".
![Alt text](<hinh 1.7.png>)
![Alt text](<hinh 1.8.png>)
2. Ở trang Data Sources, click mục **Connect data source**
![Alt text](<hinh 1.9.png>)
3. Chọn data source là Redis mà bạn muốn kết nối, như trong ảnh chụp màn hình sau và nhấp vào **Next**
![Alt text](image.png)
4. Trong phần Data source details: đối với Data source name, hãy nhập **redis**.
![Alt text](<hinh 1.37.png>)
5. The lambda function đã được triển khai như một phần của workshop này. Click vào **Select hoặc Lambda function**. Chọn **redis** và nhấp vào 'Next'
![Alt text](<hinh 1.38.png>)
6. Xem lại thông tin và nhấp vào 'Create data source'
![Alt text](<hinh 1.39.png>)
7. Click vào Data Sources và xác minh rằng new data source hiển thị
![Alt text](<hinh 1.40.png>)
8. Điều hướng trở lại query editor và chọn nguồn dữ liệu mới và xem xét liệu nó có hiển thị cơ sở dữ liệu hay không. Connector đã được triển khai và sẵn sàng để sử dụng. Bạn có thể xem xét connector trong truy vấn của mình dưới dạng **"lambda:redis"** hoặc **redis.redis**.
![Alt text](<hinh 1.41.png>)
### Redis Database và Tables with Glue Data Catalog
Vì Redis không có schema riêng nên Redis Connector không thể suy ra các cột hoặc kiểu dữ liệu từ Redis. Trình kết nối Redis cần thiết lập cơ sở dữ liệu Glue và các bảng để có thể liên kết dữ liệu với lược đồ. Cloudformation template tạo cơ sở dữ liệu Redis và các bảng cần thiết trong Glue Catalog. Mở Glue như hình ở đây:
![Alt text](image-1.png)
Bạn sẽ thấy cơ sở dữ liệu redis sau trong Glue Databases:
![Alt text](<hinh 1.42.png>)
Nhấp vào cơ sở dữ liệu redis để xem các thuộc tính cơ sở dữ liệu:
![Alt text](<hinh 1.43.png>)
redis to view các bảng:
![Alt text](<hinh 1.44.png>)
Click bảng Nation để xem schema và thuộc tính của bảng:
![Alt text](<hinh 1.45.png>)
Click vào Active Orders đang hoạt động để xem schema và thuộc tính của bảng:
![Alt text](glue6.png)
Bây giờ bạn đã thiết lập xong tất cả connectors, hãy chuyển sang chương tiếp theo để chạy các federated queries.
​