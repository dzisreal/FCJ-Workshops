---
title : "Kiểm tra kết quả chạy"
date :  "`r Sys.Date()`" 
weight : 8
chapter : false
pre : " <b> 8. </b> "
---


Ở bước này, chúng ta sẽ thử vận hành luồng **CI/CD** xem có hoạt động đúng logic đã thiết kế không, kết quả mong muốn sẽ là:
- Ghi thành công **Job's Entry** vào bảng trong **DynamoDB**.
- Tạo thành công **Glue** job.

#### Trạng thái trước test

1. Truy cập vào [giao diện quản trị dịch vụ Amazon DynamoDB](https://console.aws.amazon.com/dynamodb/home), click vào **Explore items**, chọn bảng ta tạo ở bước [6](../6-CreateDynamoDB_S3/), bảng chưa có dữ liệu sẽ trông như thế này.
![check](/images/8.Check/dynamoDB_empty.png)


2. Truy cập vào [giao diện quản trị dịch vụ AWS Glue](https://console.aws.amazon.com/glue/home), click vào **ETL jobs**, chưa có job nào được tạo.
![check](/images/8.Check/glue_empty.png)


#### Tiến hành Test

1. Update code và push lên **CodeCommit**.
![check](/images/8.Check/git_push.png)

2. **CodePipeline** tự động trigger khi có commit mới lên **CodeCommit**.
![check](/images/7.CreatePipeline/codepipeline_inprocess.png)
![check](/images/8.Check/pipeline_inprocess.png)

3. Chờ 1 lát để **Pipeline** chạy xong các stage.
![check](/images/8.Check/pipeline_done.png)

4. Kiểm tra **S3 bucket**
![check](/images/8.Check/s3_has_files.png)

5. Kiểm tra **DynamoDB**
![check](/images/8.Check/dynamoDB_has_item.png)


6. Kiểm tra **Glue**
![check](/images/8.Check/glue_has_job.png)



Chúc mừng bạn đã hoàn tất bài thực hành hướng dẫn dựng luồng **CI/CD** cơ bản với AWS. Hãy nhớ thực hiện bước dọn dẹp tài nguyên để tránh sinh chi phí ngoài ý muốn nhé.