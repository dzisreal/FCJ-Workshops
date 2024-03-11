---
title : "Tạo luồng CodePipeline"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 7. </b> "
---

Ở bước này, chúng ta sẽ tiến hành tạo pipeline **CodePipeline** tự động thực hiện quá trình **CI/CD**.

![dynamoDB](/images/1.Overview/Architect.drawio.png)

#### Tạo pipeline

1. Truy cập vào [giao diện quản trị dịch vụ CodePipeline](https://console.aws.amazon.com/codepipeline/home).
  + Click **Create pipeline** 

![pipeline](/images/7.CreatePipeline/console_pipeline.png) 

2. Tại trang setting của **CodePipeline**, ta đặt tên cho pipeline, chọn **Type** V1 và role tạo ở bước [3.1](../3-PolicyAndRole/3.1-Codepipeline/) rồi bấm **Next**.

![pipeline](/images/7.CreatePipeline/part1_write_infor_pipeline.png) 
![pipeline](/images/7.CreatePipeline/part2_write_infor_pipeline.png) 

3. Tại trang **Add source stage**, ta chọn source là **CodeCommit** sau đó chọn các thông số setting như hình rồi bấm **Next**.

![pipeline](/images/7.CreatePipeline/part3_choose_source_pipeline.png) 

4. Skip qua bước **Build stage** do trong giới hạn bài workshop này, chúng ta không có gì để test :D.

![pipeline](/images/7.CreatePipeline/part4_skip_build_pipeline.png) 

5. Tại sang **Add deploy stage**, ta chọn **Deploy provider** là S3, sau đó chọn đúng **Region** và **Bucket** vừa tạo ở bước [6](../6-CreateDynamoDB_S3/), ở ô **S3 object key**, viết folder ta muốn lưu file, **S3 bucket** sẽ tự động tạo folder đó nếu chưa có, sau đó bấm **Next**.

![pipeline](/images/7.CreatePipeline/part5_choose_deploy_pipeline.png) 

6. Review lại các setting ở bước trước và **Create** pipeline.

![pipeline](/images/7.CreatePipeline/part6_check_infor_pipeline.png) 
![pipeline](/images/7.CreatePipeline/part7_create_pipeline.png) 

7. Sau khi tạo **Pipeline** xong, chúng ta quay lại màn hình console của **CodePipeline**, sẽ thấy **Pipeline** vừa được tạo đang tự động thực hiện quá trình process **Source -> Deploy**.

![pipeline](/images/7.CreatePipeline/codepipeline_inprocess.png) 

8. Tiếp theo, ta sẽ tiến hành thêm 2 **Lambda Function** tạo ở bước [5](../5-CreateLambda/) để tự động viết **Job's Entry** vào **DynamoDB** và tạo **Glue** job.
  + Chọn **Pipeline** vừa tạo.
  ![pipeline](/images/7.CreatePipeline/part8_choose_pipeline.png) 

  + Click **Edit**.
  ![pipeline](/images/7.CreatePipeline/part9_click_edit_pipeline.png) 

  + Kéo xuống cuối trang, ở bên dưới **Deploy stage**, click chọn **Add stage**, điền tên cho **Stage** rồi click **Add stage**.
  ![pipeline](/images/7.CreatePipeline/part10_click_add_stage.png) 
  ![pipeline](/images/7.CreatePipeline/part11_add_stage.png) 


  + Click **Add action group** trong khung **Edit** của stage **Lambda** vừa tạo.
  ![pipeline](/images/7.CreatePipeline/part12_add_action_group.png) 

  + Tạo action **Lambda** tương ứng với các **Lambda Function**.
  ![pipeline](/images/7.CreatePipeline/part13_add_lambda_action.png)

  + Sau khi tạo xong 2 action **Lambda**, click **Done** rồi kéo lên trên click **Save**.
  ![pipeline](/images/7.CreatePipeline/part14_add_2_action_done.png)
  ![pipeline](/images/7.CreatePipeline/part15_save_edit.png)

  + Sau khi hoàn thành tất cả các bước, **Pipeline** của chúng ta sẽ trông như thế này :D.
  ![pipeline](/images/8.Check/pipeline_done.png)


Tiếp theo, chúng ta sẽ tiến hành kiểm tra xem luồng CI/CD của chúng ta có hoạt động đúng không ở bước [8](../8-Check/).