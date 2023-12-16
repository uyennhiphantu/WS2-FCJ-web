---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Ngày nay, những vấn đề mà doanh nghiệp đang gặp phải có thể bao gồm về hiệu suất truy vấn kém, khả năng mở rộng thấp, hoặc khả năng hiển thị dữ liệu không linh hoạt. Do đó, mục đích của workshop lần này nhằm cung cấp những kiến thức cơ bản của Amazon Athena để có thể giải quyết những nhu cầu cơ bản mà doanh nghiệp đang gặp phải. Workshop lần này không bắt buộc phải có kiến thức về Amazon Athena, nhưng nếu có thì nó là một lợi thế.

Ở mục đầu tiên này sẽ bắt đầu từ dữ liệu thu thập được từ Athena để đưa ra những phân tích và biểu diễn data thông qua QuickSight. 

**1.1 Amazon Athena là gì?**
 

- No need to open port 22 for SSH protocol, so it is more secure.
- Can be configured so that the connection does not need to go outside the internet, so it is more secure.
- No need to manage the server's private key to connect to SSH.
- Centralized management of users using AWS IAM.
- Access to the server easily and simply with one click.
- Faster access time than traditional methods like SSH
- Support many different operating systems such as Linux, Windows, MacOS
- Log the connection sessions and commands executed while connecting to the server.
  
With the above advantages, you can use Session Manager instead of using Bastion host technique to save us time and money when managing Bastion server. 