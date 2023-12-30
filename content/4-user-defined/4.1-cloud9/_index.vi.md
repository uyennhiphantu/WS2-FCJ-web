---
title : "Cloud9 IDE"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---
Trong bài lab này, chúng ta sẽ sử dụng AWS Cloud9 IDE. Cloud9 IDE environment phải có sẵn như một phần của  cloud formation stack đã được chạy trước đó.

1. Sử dụng tìm kiếm dịch vụ và nhập cloud9 như hình bên dưới.
![Alt text](<hinh 1.61.png>)
![Alt text](<hinh 1.62.png>)
2. Mở **Open IDE**
3. Sau khi **Cloud9 IDE** khởi chạy, bạn sẽ thấy một màn hình như thế này:
![Alt text](<hinh 1.63.png>)
4. Cloud9 IDE đi kèm với dung lượng ổ đĩa 10 GB mặc định, dung lượng này có thể lấp đầy nhanh chóng khi chúng ta thiết lập môi trường phát triển. Chạy lệnh bên dưới để lấy tập lệnh thay đổi kích thước rồi chạy nó để tăng kích thước ổ đĩa lên 20GB.

```
 curl https://aws-data-analytics-workshops.s3.amazonaws.com/athena-workshop/scripts/cloud9\_resize.sh > cloud9\_resize.sh 
```
​Chạy tập lệnh bằng cách đưa ra lệnh sau trên thiết bị đầu cuối cloud9. Điều này sẽ thay đổi kích thước đĩa thành 20GB.
```
sh cloud9\_resize.sh 20 
```
Kiểm tra dung lượng trống trên đĩa bằng lệnh bên dưới.
```
df -h 
```
Bạn sẽ thấy như hình dưới đây:

![Alt text](image-1.png)