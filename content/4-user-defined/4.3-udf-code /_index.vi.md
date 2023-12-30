---
title : "UDF Code và Publish"
date :  "`r Sys.Date()`" 
weight : 4.3
chapter : false
pre : " <b> 4.3. </b> "
---

1. Mở dự án

Trong IDE Cloud9 ở phía bên trái, hãy mở rộng dự án aws-athena-query-federation và điều hướng đến tệp **AthenaUDFHandler.java**. Nhấp đúp chuột vào tệp và nó sẽ mở ra để chỉnh sửa như hiển thị ở đây:
![Alt text](image.png)
2. Thêm UDF Function
Bây giờ chúng ta sẽ thêm mã UDF cho hàm Redact String để sắp xếp lại một chuỗi để chỉ hiển thị 4 ký tự cuối cùng. Chức năng UDF này có thể được sử dụng để che Credit Card Information, SSN hoặc các thông tin nhạy cảm khác như Tên khách hàng, Số điện thoại, Địa chỉ, v.v.
![Alt text](cloud9_4.png)
Hàm này lấy một chuỗi làm đầu vào và trả về một chuỗi đã được xử lý lại để chỉ hiển thị 4 ký tự cuối cùng, ví dụ: xxxx1234. Hàm UDF lấy tên cột làm đầu vào từ nguồn dữ liệu đang được sử dụng như một phần của truy vấn, xử lý tên cột đó bằng mã hàm lambda rồi trả về dữ liệu cho Athena.

```
    /** Redact a string to show only the last 4 characters
     * 
     * 
     * 
     * @param input the string to redact
     * @return redacted string
     */
    public String redact(String input)
    {
        String redactedString = new StringBuilder(input).replace(0, input.length() - 4, new String(new char[input.length() - 4]).replace("\0", "x")).toString(); 
        return redactedString;
    }
```
Bạn có thể sao chép đoạn mã ở dòng 61 trong **AthenaUDFHandler.java** hoặc bạn có thể lấy mã UDF đã sửa đổi bằng cách đưa ra lệnh sau:
```
curl https://aws-data-analytics-workshops.s3.amazonaws.com/athena-workshop/scripts/AthenaUDFHandler.java > athena-udfs/src/main/java/com/amazonaws/athena/connectors/udfs/AthenaUDFHandler.java 
```
Sau khi sao chép tệp, bạn có thể mở tệp đó trong Cloud9 IDE để xem nội dung của tệp.

3. **Build the JAR File** Lưu tệp và chạy mvn clean install để xây dựng dự án của bạn. Sau khi xây dựng thành công, một tệp JAR sẽ được tạo trong thư mục đích của dự án của bạn có tên ArtifactId-version.jar, trong đó ArtifactId là tên bạn đã cung cấp trong dự án Maven, ví dụ: athena-udfs.

```
cd ~/environment/aws-athena-query-federation/athena-udfs/ 
mvn install -DskipTests
```
