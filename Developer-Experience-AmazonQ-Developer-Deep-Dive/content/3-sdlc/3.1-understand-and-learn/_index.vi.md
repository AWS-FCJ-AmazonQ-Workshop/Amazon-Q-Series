---
title: "SDLC Phase: Học và Hiểu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

Giai đoạn này tập trung vào knowledge acquisition, system understanding, và team onboarding. Amazon Q Developer tăng tốc quá trình học tập thông qua contextual explanations và knowledge transfer.

#### Bắt đầu

Truy cập Amazon Q Developer trong AWS Console bằng cách click icon ở phía bên phải. Đối với participants tham gia AWS event, tham khảo phần Configuration để setup account.

![alt text](/images/3-sdlc/3.1-understand-and-learn/image.png?width=90pc)

#### Example 1: AWS Resource Discovery

**Scenario**: Hiểu current AWS environment của bạn

**Prompt**:
```
How many running EC2 instances do I have?
```

**Use Case**: Nhanh chóng assess infrastructure inventory và resource utilization trong AWS account.

![alt text](/images/3-sdlc/3.1-understand-and-learn/image-1.png?width=40pc)

#### Example 2: Knowledge Gap Resolution

**Scenario**: Strategic technology adoption đòi hỏi hiểu Domain Driven Design (DDD)

**Prompt**:
```
Help me understand Domain Driven Design using an online e-commerce application example. 
Show me how to implement DDD patterns on AWS with serverless and microservices.
```

**Use Case**: Khắc phục knowledge gaps cho enterprise digital transformation initiatives.

![alt text](/images/3-sdlc/3.1-understand-and-learn/image-2.png?width=40pc)

{{% notice tip %}}
**Context Management**: Amazon Q duy trì conversation context trong sessions. Sử dụng "New conversation" để clear context khi chuyển topics để có responses chính xác hơn.
{{% /notice %}}

#### Example 3: Programming Language Transition

**Scenario**: Developer onboarding từ Python sang Java/C# trong enterprise environment

{{% notice info %}}
**Chuyển sang IDE** và mở Q Chat cho example này.
{{% /notice %}}

**Prompt**:
```
I have Python background and need to learn Java quickly. 
Explain core Java concepts focusing on differences and similarities with Python. 
Use practical examples for comparison.
```

**Use Case**: Tăng tốc developer onboarding và cross-language knowledge transfer.

![alt text](/images/3-sdlc/3.1-understand-and-learn/image-3.png?width=40pc)

#### Example 4: Framework Learning

**Scenario**: Hiểu .NET Entity Framework và LINQ mà không có documentation hoặc mentorship

**Prompt**:
```
I come from Python background and don't know Entity Framework or LINQ. 
Explain in simple terms using Python analogies. 
Format: "In Python we have [example] whereas in C#, we have [example]"
```

**Use Case**: Self-directed learning của enterprise frameworks và patterns.

{{% notice info %}}
**IDE Context Management**: Clear conversation context bằng cách click (+) cho new chat tab hoặc gõ `/clear` trong current window.
{{% /notice %}}
