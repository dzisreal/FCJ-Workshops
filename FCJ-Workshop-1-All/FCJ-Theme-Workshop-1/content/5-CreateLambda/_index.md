---
title : "Tạo các Lambda"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---


Ở bước này, chúng ta sẽ tiến hành tạo và viết các **Function Lambda** cho để đọc các file code và file cấu hình từ **S3**, sau đó thực hiện việc lưu **Job's Entry** vào **DynamoDB** và tạo **Glue Job** từ các file tương ứng.

![lambda](/images/5.CreateLambda/NoteLambda.png) 



#### Tạo Lambda Function

1. Truy cập vào [giao diện quản trị dịch vụ AWS Lambda](https://console.aws.amazon.com/lambda/home)
  + Click **Functions** , sau đó click **Create function**.

![lambda](/images/5.CreateLambda/console_create_lambda.png) 

2. Tại trang **Create function**.
  + Chúng ta lần lượt điền click chọn và điền thông tin theo các bước, ở phần **Role**, chúng ta chọn **Role** đã tạo ở bước [3.2](../3-PolicyAndRole/3.2-Lambda/).
  
![lambda](/images/5.CreateLambda/part1_create_lambda.png) 
![lambda](/images/5.CreateLambda/part2_create_lambda.png) 


3. Làm các bước trên 2 lần để tạo 2 **Lambda Function** như hình.

![lambda](/images/5.CreateLambda/console_all_lambda.png) 

4. Mặc định, các **Lambda Function** sẽ có **Time out** là **3s**, chúng ta sẽ nâng chỉ số này lên để đáp ứng cho trường hợp khối lượng công việc cần nhiều hơn **3s** để xử lý, ta sẽ làm tương tự ở **Lambda Function** còn lại.

![lambda](/images/5.CreateLambda/choose_function.png)
![lambda](/images/5.CreateLambda/choose_function_cfg.png)
![lambda](/images/5.CreateLambda/increase_timeout_function.png)


#### Script 
  
Để **Lambda Function** tương tác được với các service khác của AWS, chúng ta sẽ sử dụng thư viện **Boto3** do AWS phát triển, thông tin thêm về **Boto3** mọi người có thể đọc thêm ở [đây](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html).

Script sử dụng trong 2 **Lambda Function** mọi người có thể tham khảo ở [đây](https://github.com/dzisreal/FCJ-Workshop-1/tree/56a2e1f8bd6dfbe9a7d9f9ddeb0ad5502b993341/lambdas_script).

Tiếp theo, chúng ta sẽ tiến hành tạo bảng DynamoDB để lưu **Job's Entry**.