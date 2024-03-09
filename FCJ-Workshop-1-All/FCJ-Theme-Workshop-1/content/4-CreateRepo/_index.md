---
title : "Tạo repository CodeCommit"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---


Các file của workshop sẽ được viết ở máy local, sau đó push lên ***CodeCommit*** để lưu trữ và phục vụ cho quá trình ***CI/CD***, hình bên dưới là cấu trúc của 1 ***Repository CodeCommit***

![S3](/images/4.CreateRepo/createrepo.png)

Trong phần này chúng ta sẽ tiến hành tạo ***Repository CodeCommit*** và thực hiện tạo ***HTTPS Git credentials for AWS CodeCommit*** để có thể remote từ máy local, sau đó tiến hành push code lên

### Nội dung:

  - [Tạo ***Repository CodeCommit***](./4.1-CreateRepo/)
  - [Tạo ***HTTPS Git credentials for AWS CodeCommit*** và remote từ ***Local***](./4.2-Remote/)
