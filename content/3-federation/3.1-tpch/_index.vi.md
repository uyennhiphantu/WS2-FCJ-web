---
title : "TPCH Database & Tables"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---
### Thử nghiệm dữ liệu & người dùng
Để thể hiện khả năng federation của Athena, một tập dữ liệu mẫu đang được sử dụng trong workshop này cùng với các bảng mẫu và nguồn dữ liệu mẫu.

Hãy cùng xem qua các thử nghiệm datasets & data sources sau:

### TPCH Database & Tables
Dữ liệu TPCH, một tập dữ liệu công cộng, sẽ được sử dụng cho buổi workshop này. Dataset này là một chuẩn đoán hỗ trợ quyết định. Nó bao gồm một loạt các truy vấn linh hoạt theo hướng kinh doanh và các sửa đổi dữ liệu đồng thời. Các truy vấn và dữ liệu trong cơ sở dữ liệu đã được lựa chọn để có tính phổ quát trong ngành công nghiệp. Kiểm chuẩn (Benchmark) này mô tả các hệ thống hỗ trợ quyết định xem xét các khối lượng dữ liệu lớn, thực hiện các truy vấn với độ phức tạp cao và cung cấp câu trả lời cho những câu hỏi kinh doanh quan trọng. TPCH bao gồm tám bảng riêng biệt (Base Tables). Mối quan hệ giữa các cột trong các bảng này được minh họa trong biểu đồ sau: 
![Alt text](image.png)
Trong workshop này, chúng ta sẽ tập trung vào các bảng sau từ cơ sở dữ liệu TPC:
- customer
- supplier
- orders
- part
- partsupp
- lineitem
- nation
Toàn bộ từ điển TPCH data có sẵn ở đây: chèn link