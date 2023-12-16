---
title : "Các bước chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

### Cloudformation Template

Trước khi bắt đầu workshop Amazon Athena này, bạn cần tạo các tài nguyên AWS cần thiết. Để thực hiện việc này, chúng tôi cung cấp mẫu AWS CloudFormation để tạo stack chứa tài nguyên. Khi bạn tạo stack, AWS sẽ tạo một số tài nguyên trong tài khoản của bạn.

Để khởi chạy CloudFormation stack, hãy nhấp vào Launch Stack.
  
{{% notice note %}}
Các mẫu này được tạo cho vùng us-east-1 region (N. Virginia) và sẽ không hoạt động ở các vùng khác. Không thay đổi bất kỳ tham số Cơ sở dữ liệu mặc định nào trong CloudFormation
{{% /notice %}}

**Labs - Athena Basics:**

{{% notice note %}}
CloudFormation stack sẽ mất khoảng 5 phút để hoàn thành.
{{% /notice %}}

CloudFormation stack sẽ tạo ra những người dùng IAM cần thiết, Athena Workgroups và Athena Named Queries dùng để thử nghiệm các bài labs. Kiểm tra bảng điều khiển CloudFormation và đợi trạng thái hiển thị CREATE_COMPLETE như bên dưới:

![image](<hinh 1.png>)

Nhấp vào cloudformation stack và chuyển đến outputs tab, nó sẽ hiển thị tên S3 bucket được tạo cho workshop này:
![image](<hinh 2.png>)
