---
title : "Tạo HTTPS Git credentials for AWS CodeCommit và remote từ Local"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---


Trong bước này, chúng ta sẽ tạo ***HTTPS Git credentials for AWS CodeCommit*** và tiến hành remote ***Repository CodeCommit*** từ Local

#### Tạo **S3 Bucket**

1. Truy cập vào [giao diện quản trị của dịch vụ IAM](https://us-east-1.console.aws.amazon.com/iamv2/home).
  + Click **Users** và chọn user mình đang sử dụng.

![Connect](/images/4.CreateRepo/choose_user.png)

2. Click chuyển sang tab ***Security credentials***.

![Connect](/images/4.CreateRepo/click_security_credentials.png)

3. Kéo chuột xuống phía dưới và click ***Generate credentials***.

![Connect](/images/4.CreateRepo/generate_credentials.png)

4. Click ***Download credentials*** để tải về file thông tin đăng nhập phục vụ cho bước Remote phía sau

![Connect](/images/4.CreateRepo/popup_generate_credentials.png)

5. Quay lại giao diện console ***CodeCommit***, click vào mục ***Repositories***, ***Repository*** vừa tạo ở phần [4.1](../4.1-CreateRepo/) sẽ hiện trên màn hình, click copy link ***HTTPS*** của ***Repository***.

![Connect](/images/4.CreateRepo/copy_https_repo.png)

6. Chạy câu lệnh ***git clone*** với link ***HTTPS*** vừa copy, cửa sổ popup đăng nhập hiện lên, chúng ta sẽ điền thông tin đăng nhập vừa tải ở bước 4

![Connect](/images/4.CreateRepo/remote_and_log_in_popup.png)

7. Sau khi remote thành công, từ bây giờ chúng ta có thể push code từ Local lên ***Repository CodeCommit*** bằng câu lệnh ***Git*** như bình thường, ***Repository** của chúng ta sẽ gồm 3 folder chính như hình, mọi người có thể tham khảo thêm thông tin các file ở [link](https://github.com/dzisreal/FCJ-Workshop-1.git) này.

![Connect](/images/4.CreateRepo/repo_detail.png)