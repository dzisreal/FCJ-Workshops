---
title : "Tạo bảng DynamoDB và S3 Bucket"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

Ở bước này, chúng ta sẽ tiến hành tạo bảng **DynamoDB** để lưu **Job's Entry**.

![dynamoDB](/images/6.CreateDynamoDB_S3/notedynamodb.png) 


#### Tạo bảng DynamoDB

1. Truy cập vào [giao diện quản trị dịch vụ Amazon DynamoDB](https://console.aws.amazon.com/dynamodbv2/home)
  + Click **Create table** , sau đó ở giao diện **Create table**, ta lần lượt điền các thông tin **Table name** và **Partition key**, ở giới hạn bài lab này thì **Partition key** sẽ dùng để phân biệt các bảng cần **Transform** bằng **Glue**.

![lambda](/images/6.CreateDynamoDB_S3/console_dynamodb.png) 
![lambda](/images/6.CreateDynamoDB_S3/write_table_info.png) 
![lambda](/images/6.CreateDynamoDB_S3/create_table.png) 

2. Tại trang **Tables** của **DynamoDB**, chúng ta có thể thấy bảng vừa tạo.

![dynamoDB](/images/6.CreateDynamoDB_S3/show_all_table.png) 


#### Tạo S3 Bucket

1. Truy cập vào [giao diện quản trị dịch vụ Amazon S3](https://console.aws.amazon.com/s3/home)
  + Click **Create bucket** , sau đó ở giao diện **Create bucket**, ta lần lượt điền các thông tin **AWS Region** và **Bucket name**, sau đó kéo xuống cuối trang và click **Create bucket**

![s3](/images/6.CreateDynamoDB_S3/console_s3.png) 
![s3](/images/6.CreateDynamoDB_S3/write_bucket_info.png) 
![s3](/images/6.CreateDynamoDB_S3/create_bucket.png) 

Vậy là ta vừa tạo thành công 1 bảng **DynamoDB** và 1 bucket **S3**, tiếp theo chúng ta sẽ tiến hành tạo **CodePipeline**.
