---
title : "Tái sử dụng Kết quả Truy vấn"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 3.6. </b> "
---
---

Khi chạy lại truy vấn trong Athena, chúng ta có thể tùy ý chọn sử dụng lại kết quả truy vấn được lưu trữ gần đây nhất. Tùy chọn này có thể tăng hiệu suất và giảm chi phí về số lượng bytes được quét. Ví dụ: việc sử dụng lại kết quả truy vấn sẽ hữu ích nếu biết rằng kết quả sẽ không thay đổi trong một khung thời gian nhất định. Chúng ta có thể chỉ định thời gian tối đa để sử dụng lại kết quả truy vấn. Athena sử dụng kết quả được lưu trữ miễn là nó không cũ hơn khoảng thời gian tồn tại mà chúng ta chỉ định.

**Xác minh tính năng của Tái sử dụng Kết quả Truy vấn khả dụng**
Mở bảng điều khiển Athena bằng cách nhập **Athena** vào thanh tìm kiếm ở đầu màn hình. Chọn **Athena** từ kết quả tìm kiếm.

Để sử dụng lại kết quả truy vấn, trước tiên vui lòng xác minh xem tùy chọn 'Reuse query results’ (được đánh dấu trong hình dưới đây) đã được bật hay chưa.
![image](<hinh 37.png>)
Nếu nó được bật (bạn có thể kiểm tra bằng cách chọn chuyển đổi Reuse query results để xem nó đã bật hay chưa), sau đó bỏ qua phần này và chuyển xuống phần tính năng **Testing the reuse query results feature section below.** Nếu không, hãy hoàn thành các bước sau để bật tính năng này:

1. Chọn **Workgroups** trong **Administration** menu được thả xuống trên menu tab bên trái trên màn hình (được đánh dấu trong ảnh chụp màn hình bên dưới) và **primary** workgroup từ danh sách nhóm làm việc.
![image](<hinh 38.png>)
2. Nhấp vào nút **Edit** ở phía trên bên phải của trang để chỉnh sửa cài đặt workgroup.
![image](<hinh 39.png>)
3. Trong phần **Upgrade Query Engine**, nhấp vào nút radio **Manual**. Sau đó chọn **Athena engine version 3** từ danh sách thả xuống của **Query engine version**.
![image](<hinh 40.png>)
4. Chọn **Save Changes** ở góc dưới bên phải.
![image](<hinh 41.png>)

**Kiểm tra tính năng Tái sử dụng Kết quả Truy vấn**
Để xác minh tính năng tái sử dụng:

    1. Điều hướng quay lại **Query editor**
    2. Chọn biểu tượng + để thêm tab mới
    3. Sao chép và dán truy vấn bên dưới vào query editor.

``
select c.customer_id,concat("firstname",' ',"lastname") as full_name,
sum(cast(price as decimal(6,2))) as lifetime_value,
count("timestamp") as lifetime_purchase_count,
sum(cast(price as decimal(6,2))) /count("timestamp") as average_spend_per_purchase
from customers_parquet c join sales_parquet s on c.customer_id = s.customer_id
group by c.customer_id,concat("firstname",' ',"lastname"),c.country;
``

4.  Nhấn **Reuse query results** sang vị trí tắt.
5. Chọn **Run**
![image](<hinh 42.png>)
6. Ghi lại số liệu thống kê cho Truy vấn bao gồm các giá trị Run time và Data scanned.
![image](<hinh 43.png>)
7. Nhấp vào nút **Reuse query results** để bật.
![image](<hinh 44.png>)
8. Nhấp vào biểu tượng **edit** (tức là biểu tượng bút chì) bên dưới 'Reuse query results’. Đặt thời gian sử dụng lại là 30 phút rồi nhấn nút **Confirm**.
![image](<hinh 45.png>)
9. Chạy lại truy vấn bằng cách bấm vào nút **Run again**. Lưu ý sự khác biệt về Run time và Data scanned so với lần chạy ban đầu.
![image](<hinh 46.png>)
10. Đi tới tab **Recent Queries** trong tab query editor và kiểm tra cột 'Cache’ để xem giá trị 'Result reuse’ đã được thêm vào trong quá trình thực thi. Điều này cho thấy rằng để thực hiện truy vấn đó, kết quả đã được sử dụng lại.

{{% notice note %}}
Bạn có thể cần phải cuộn qua để tìm cột Cache
{{% /notice %}}
![image](<hinh 47.png>)

11. Chạy lại truy vấn và reuse time khác nhau sau khi xác minh. Ví dụ: thay đổi **reuse time** từ 30 phút thành 1 phút bằng cách sử dụng hướng dẫn ở Bước 7. Chạy lại truy vấn của bạn và kiểm tra xem nó có sử dụng lại kết quả hay không.

Bây giờ bạn đã khám phá thành công tính năng query results reuse trong Amazon Athena.