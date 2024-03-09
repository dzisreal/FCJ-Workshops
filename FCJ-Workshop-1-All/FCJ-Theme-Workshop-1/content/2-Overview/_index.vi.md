---
title : "Tổng quan kiến trúc"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

![ConnectPrivate](/images/1.Overview/Architect.png)

Trong bài workshop này, chúng ta sẽ cùng nhau dựng 1 luồng **CI/CD** cơ bản sử dụng các service của **AWS**, bao gồm:
- CodeCommit
- CodeDeploy
- CodePipeline (CodeCommit -> CodeDeploy -> Lambda)
- Lambda
- S3
- DynamoDB
- Glue


Luồng **CI/CD** này của chúng ta sẽ hoạt động như sau:
1. Lập trình viên push code lên **CodeCommit**.
2. **CodeDeploy** đồng bộ các file trong **repository CodeCommit** lên **S3 bucket**.
3. **Lambda (1)** đọc file **Job's Entry** từ **S3 bucket** và lưu vào **DynamoDB**.
4. **Lambda (2)** đọc file **Job's Config** và **Job's Script** từ **S3 bucket**, sau đó tạo **Glue job** theo thông tin cấu hình trong file.

{{% notice note %}}
Luồng **CI/CD** thông thường sẽ có sử dụng cả **CodeBuild** để chạy các bài test, nhưng trong giới hạn bài workshop này các file sẽ chỉ là file khai báo và script thôi nên chúng ta sẽ bỏ qua bước "**Build**".
{{% /notice %}}