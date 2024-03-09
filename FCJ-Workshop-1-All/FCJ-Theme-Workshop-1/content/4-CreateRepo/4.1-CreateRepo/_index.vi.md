---
title : "Tạo Repository CodeCommit"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---


#### Tạo Repository
{{% notice warning %}}
Khi tạo ***Repository CodeCommit***, mọi người cần chú ý đến **Region**, ở link truy cập bên dưới, vì mình làm workshop ở **Region Sydney** nên link sẽ điều hướng đẫn **Sydney**, mọi người cần điều chỉnh lại về đúng **Region** của mình 
{{% /notice %}}

1. Truy cập vào [giao diện quản trị dịch vụ CodeCommit](https://ap-southeast-2.console.aws.amazon.com/codesuite/codecommit/start?region=ap-southeast-2)
  + Click ***Create repository***.

![Connect](/images/4.CreateRepo/clickcreaterepo.png)

2. Điền ***Repository name*** và ***Description***, sau đó click ***Create***.
 
![Connect](/images/4.CreateRepo/add_name_create_repo.png) 

3. Quay lại giao diện console ***CodeCommit***, click vào mục ***Repositories***, ***Repository*** vừa tạo sẽ hiện trên màn hình.
4. 
![Connect](/images/4.CreateRepo/show_repo.png) 
 

Tiếp theo chúng ta sẽ tiến hành các bước setup để có thể remote đến ***Repository*** từ Local.