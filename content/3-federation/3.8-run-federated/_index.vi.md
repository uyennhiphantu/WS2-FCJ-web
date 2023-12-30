---
title : "Run Federated Queries "
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 3.8. </b> "
---
---

Bây giờ, Connectors đã được triển khai, chúng ta có thể chạy các truy vấn Athena mà nó sử dụng connectors:

- Đi tới bảng điều khiển Athena: https://console.aws.amazon.com/athena/. Click vào Bắt đầu.

- Đảm bảo bạn đang ở trong Workgroup: **V2EngineWorkGroup**. Để sử dụng tính năng federated queries và các tính năng khác như features do User Defined Function (UDFs) and ML Inference, các truy vấn cần chạy trên công cụ Athena phiên bản 2. V2EngineWorkGroup được cấu hình với v2 engine. Nếu bạn không thuộc workgroup này, hãy click vào Workgroup và chọn V2EngineWorkGroup
​![Alt text](<hinh 1.46.png>)
Click vào Saved Queries và Select Sources
![Alt text](<hinh 1.47.png>)
Bạn sẽ thấy các truy vấn như thế này:
![Alt text](<hinh 1.48.png>)
Các truy vấn này kiểm tra chức năng Athena Connector của bạn cho từng data source và bạn có thể đảm bảo rằng bạn có thể trích xuất dữ liệu từ từng data source trước khi chạy các truy vấn phức tạp hơn, liên quan đến các nguồn dữ liệu khác nhau. Select truy vấn đầu tiên và nhấp vào click **Run query**. Khi truy vấn thực hiện thành công, bạn sẽ thấy kết quả như thế này:
![Alt text](<hinh 1.49.png>)
Bây giờ bạn có thể quay lại Saved Queries và thử các truy vấn sau:

- FetchActiveOrderInfo
- ProfitBySupplierNationByYr
- OrdersRevenueDateAndShipPrio
- SuppliersWhoKeptOrdersWaiting
- ShippedLineitemsPricingReport**
