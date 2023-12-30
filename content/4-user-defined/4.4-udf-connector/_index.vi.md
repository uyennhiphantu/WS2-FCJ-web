---
title : "UDF Connector Setup"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.4. </b> "
---

Bây giờ UDF Connector code đã được xuất bản, chúng ta có thể cài đặt trình kết nối UDF để sử dụng với Athena:

- Nhấp vào ứng dụng **AthenaUserDefinedFunctions** trong ứng dụng  **Privateapplications** từ **Serverless Application Repository.**

**Thực hiện theo các hướng dẫn được liệt kê bên dưới để vào Cài đặt ứng dụng:**

- **Application Name:** Để nguyên tên mặc định - **AthenaUserDefinedFunctions.**
- SecretNameorPrefix: Nhập tên bí mật nếu bạn đã lưu trong Secrets Manager, nếu không hãy nhập **database-*.**
- **LambdaFunctionName:** Nhập **customudf**

Nó sẽ giống như thế này:
![Alt text](image.png)
Bấm vào **Deploy** để triển khai connector.

- Chuyển sang chương tiếp theo khi UDF được triển khai thành công. Nó sẽ giống như thế này:
![Alt text](image-1.png)