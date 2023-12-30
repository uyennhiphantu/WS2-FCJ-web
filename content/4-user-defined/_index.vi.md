---
title : "User Defined Functions"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

Amazon Athena hiện đã hỗ trợ các user-defined functions (UDFs), một tính năng cho phép khách hàng viết các functions custom scalar và gọi chúng trong các truy vấn SQL. Trong khi Athena cung cấp các hàm tích hợp sẵn (built-in functions), UDFs cho phép khách hàng thực hiện xử lý tuỳ chỉnh như nén và giải nén dữ liệu, che giấu thông tin nhạy cảm hoặc áp dụng decryption tuỳ chỉnh. Khách hàng có thể viết các UDF của họ bằng Java sử dụng Athena Query Federation SDK. Khi một UDF được sử dụng trong một truy vấn SQL gửi đến Athena, nó được gọi và thực thi trên AWS Lambda. UDFs có thể được sử dụng trong cả các mệnh đề SELECT và FILTER của một truy vấn SQL. Người dùng có thể gọi nhiều UDF trong cùng một truy vấn.

Các lab này bao gồm các chức năng cơ bản của Athena UDF, viết UDF của riêng bạn, xây dựng và xuất bản UDF của bạn đến  Serverless Application Repository, cấu hình ứng dụng kết nối UDF sau đó sử dụng UDF trong các truy vấn Athena.

Một số trường hợp sử dụng như che giấu thông tin nhạy cảm, thông tin PII, Credit Card, SSN, v.v. có thể được triển khai như một UDF. Thêm tài liệu về việc truy vấn Athena UDF có thể được tìm thấy tại đây: Truy vấn UDF

Thực hiện theo từng bước một để hoàn thành các bài labs này:
- 4.1 [Cloud9 IDE](4.1-cloud9)
- 4.2 [Setting Development Environment](4.2-setting)
- 4.3 [UDF Code and Publish](4.3-udf-code)
- 4.4 [UDF Connector Setup](4.4-udf-connector)
- 4.5 [Querying with UDF](4.5-aurora-connector)
