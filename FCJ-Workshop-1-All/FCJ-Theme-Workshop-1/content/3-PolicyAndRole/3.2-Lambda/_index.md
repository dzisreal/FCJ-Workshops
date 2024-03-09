---
title : "Tạo Role cho Lambda"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
![SSMPublicinstance](/images/3.CreateRole/iam_logo.png) 

1. Truy cập vào [giao diện quản trị của dịch vụ IAM](https://us-east-1.console.aws.amazon.com/iamv2/home).
  + Click chọn ***Roles***.
  + Click ***Create role***.

![Connect](/images/3.CreateRole/01-CreateRole.png)

  + Click ***Custom trust policy***.
  + Sửa ***"Custom trust policy"*** như hình.
  + Click ***Next***

![Connect](/images/3.CreateRole/trustpolicylambda.png)

  + Tại trang ***Add permissions***, lần lượt thêm các policy ***AmazonDynamoDBFullAccess, AmazonS3FullAccess, AWSCodeCommitFullAccess, AWSGlueServiceRole*** do các hàm lambda của chúng ta cần tương tác với các service đó.

![Connect](/images/3.CreateRole/Lambdapolicy.png)

  + Vì ***Lambda***.

  + Click ***Next***.
  + Tại trang ***Name, review, and create***, điền ***Role name*** và ***Description***, kiểm tra lại ***Trust policy*** và ***Add permissions***, sau đó bấm ***Create role***
  + 
![Connect](/images/3.CreateRole/Lambdaaddname.png)
![Connect](/images/3.CreateRole/finalcreaterole.png)

{{% notice note %}}
Sau khi ***Create role***, chúng ta sẽ vào lại giao diện Console của IAM, tìm kiếm tên ***Role*** và click vào kiểm tra lại các setting, phần này mình hơi lười nên không có ảnh đâu, mọi người tự làm nha (>_<).
{{% /notice %}}

