---
title: "Comment Đơn Dòng"
date: 2023-08-17T00:00:00-00:00
weight: 2
chapter: false
pre: "<b>3.3.2.2 </b>"
---

# Prompt Comment Đơn Dòng

## Tổng Quan
Prompt comment đơn dòng sử dụng comment nội tuyến để tạo ra các gợi ý code cụ thể. Amazon Q Developer phân tích ngữ cảnh comment và cung cấp các implementation code phù hợp ngay sau comment.

## Trường Hợp Sử Dụng
- Tạo implementation function đơn giản
- Tạo variable assignment
- Thêm logic điều kiện
- Implement thuật toán cơ bản

## Thực Hành Tốt

### 1. Cụ Thể và Rõ Ràng
```python
# Calculate the factorial of a number using recursion
```

### 2. Bao Gồm Ngữ Cảnh
```javascript
# Validate email format using regex pattern
```

### 3. Chỉ Định Hành Vi Mong Đợi
```java
// Sort array in ascending order using bubble sort
```

## Ví Dụ Implementation

### Ví Dụ Python
```python
# Create a function to check if a number is prime
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True
```

### Ví Dụ JavaScript
```javascript
// Convert string to title case
function toTitleCase(str) {
    return str.replace(/\w\S*/g, (txt) => 
        txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase()
    );
}
```

## Lợi Ích Chính
- **Implementation Nhanh**: Tạo code nhanh chóng cho các tác vụ đơn giản
- **Nhận Thức Ngữ Cảnh**: Tận dụng code xung quanh cho gợi ý tốt hơn
- **Cú Pháp Tối Thiểu**: Format comment đơn giản không cần cú pháp đặc biệt
- **Không Phụ Thuộc Ngôn Ngữ**: Hoạt động trên nhiều ngôn ngữ lập trình

## Mẹo Sử Dụng Hiệu Quả
1. Đặt comment ngay phía trên nơi code cần được tạo
2. Sử dụng ngôn ngữ mô tả rõ ràng ý định
3. Bao gồm gợi ý về parameter hoặc return type khi phù hợp
4. Giữ comment ngắn gọn nhưng có thông tin
