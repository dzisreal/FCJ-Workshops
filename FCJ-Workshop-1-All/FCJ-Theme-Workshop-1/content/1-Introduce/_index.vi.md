---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Trong môi trường phát triển phần mềm ngày nay, việc duy trì tính linh hoạt, tốc độ và độ tin cậy trong quy trình phát triển và triển khai ứng dụng là cực kỳ quan trọng. ***Continuous Integration (CI)*** và ***Continuous Delivery/Deployment (CD)*** là những phương pháp tiếp cận tốt nhất giúp đạt được mục tiêu này. ***CI/CD*** giúp tự động hóa các bước từ việc tích hợp mã nguồn, xây dựng ứng dụng, thử nghiệm và triển khai ứng dụng lên môi trường sản xuất một cách suôn sẻ và liên tục.

**Hoàn cảnh sử dụng CI/CD:**

Một nhóm phát triển phần mềm thường gặp phải thách thức về việc duy trì tính nhất quán và chất lượng của mã nguồn khi làm việc trong một môi trường động với nhiều lập trình viên. Việc triển khai thủ công có thể dẫn đến lỗi, trì hoãn và thậm chí là sự cố hệ thống nghiêm trọng. ***CI/CD*** giải quyết vấn đề này bằng cách tự động hóa quy trình xây dựng và triển khai, giúp phát hiện và sửa lỗi sớm, giảm thời gian đưa sản phẩm ra thị trường và tăng cường phản hồi từ người dùng cuối.

**Sử dụng CI/CD trên AWS**

AWS cung cấp bộ công cụ hỗ trợ CI/CD bao gồm một loạt các dịch vụ có thể tích hợp sâu cùng nhau, có thể đáp ứng nhu cầu xây dựng luồng CI/CD một cách tối ưu nhất cho quy mô và độ phức tạp dự án.
Bộ công cụ bao gồm các dịch vụ chính như ***AWS CodeCommit, AWS CodeBuild, AWS CodeDeploy, AWS CodePipeline*** được thiết kế để làm việc một cách mượt mà với các dịch vụ ***AWS*** khác như ***S3, Lambda, EC2, ECS, EKS***, ...
