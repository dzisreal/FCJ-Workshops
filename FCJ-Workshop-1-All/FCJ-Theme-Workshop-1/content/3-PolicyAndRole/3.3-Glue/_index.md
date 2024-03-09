---
title : "Tạo Role cho Glue"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---
![SSMPublicinstance](/images/3.CreateRole/iam_logo.png) 

1. Truy cập vào [giao diện quản trị của dịch vụ IAM](https://us-east-1.console.aws.amazon.com/iamv2/home).
  + Click chọn ***Roles***.
  + Click ***Create role***.

![Connect](/images/3.CreateRole/01-CreateRole.png)

  + Click ***Custom trust policy***.
  + Sửa ***"Custom trust policy"*** như hình.
  + Click ***Next***

![Connect](/images/3.CreateRole/trustpolicyglue.png)

  + Tại trang ***Add permissions***, lần lượt thêm các policy ***AmazonS3FullAccess, AWSGlueServiceRole*** do các job ***Glue*** của chúng ta cần các quyền tương ứng.

![Connect](/images/3.CreateRole/gluepolicies.png)

  + Click ***Next***.
  + Tại trang ***Name, review, and create***, điền ***Role name*** và ***Description***, kiểm tra lại ***Trust policy*** và ***Add permissions***, sau đó bấm ***Create role***
  + 
![Connect](/images/3.CreateRole/glueaddname.png)
![Connect](/images/3.CreateRole/finalcreaterole.png)

{{% notice note %}}
Sau khi ***Create role***, chúng ta sẽ vào lại giao diện Console của IAM, tìm kiếm tên ***Role*** và click vào kiểm tra lại các setting, phần này mình hơi lười nên không có ảnh đâu, mọi người tự làm nha (>_<).
{{% /notice %}}

