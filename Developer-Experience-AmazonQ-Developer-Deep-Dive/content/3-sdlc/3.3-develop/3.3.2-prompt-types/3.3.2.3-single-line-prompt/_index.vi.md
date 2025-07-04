---
title: "Prompt Đơn Dòng"
date: 2023-08-17T00:00:00-00:00
weight: 3
chapter: false
pre: "<b>3.3.2.3 </b>"
---

# Prompt Đơn Dòng

## Tổng Quan
Prompt đơn dòng là những hướng dẫn ngắn gọn, một dòng để hướng dẫn Amazon Q Developer tạo ra các đoạn code cụ thể. Những prompt này lý tưởng cho các tác vụ tạo code nhanh và implementation đơn giản.

## Đặc Điểm
- **Ngắn Gọn**: Một dòng text mô tả
- **Rõ Ràng**: Hướng dẫn rõ ràng và không mơ hồ
- **Cụ Thể**: Tập trung vào một task hoặc function duy nhất
- **Nhận Thức Ngữ Cảnh**: Tận dụng ngữ cảnh code hiện có

## Mẫu Phổ Biến

### 1. Prompt Tạo Function
```python
# Create a function to validate password strength
# Generate a method to calculate compound interest
# Write a function to merge two sorted arrays
```

### 2. Prompt Xử Lý Dữ Liệu
```javascript
// Convert JSON string to object
// Filter array for positive numbers only
// Remove duplicates from list
```

### 3. Implementation Thuật Toán
```java
// Implement binary search algorithm
// Create quicksort function
// Generate Fibonacci sequence
```

## Thực Hành Tốt

### 1. Sử Dụng Động Từ Hành Động
```python
# Calculate monthly payment for loan
# Validate user input format
# Convert temperature from Celsius to Fahrenheit
```

### 2. Bao Gồm Input/Output Mong Đợi
```javascript
// Parse CSV string into array of objects
// Format date to MM/DD/YYYY string
// Generate random password with 8 characters
```

### 3. Chỉ Định Chi Tiết Implementation
```python
# Sort dictionary by values in descending order
# Connect to MySQL database using connection pool
# Encrypt text using AES-256 encryption
```

## Ví Dụ Implementation

### Ví Dụ Python
```python
# Create a function to find the longest word in a sentence
def find_longest_word(sentence):
    words = sentence.split()
    return max(words, key=len)
```

### Ví Dụ JavaScript
```javascript
// Generate array of random numbers between 1 and 100
function generateRandomArray(size) {
    return Array.from({length: size}, () => Math.floor(Math.random() * 100) + 1);
}
```

### Ví Dụ Java
```java
// Check if string is a palindrome
public boolean isPalindrome(String str) {
    String cleaned = str.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();
    return cleaned.equals(new StringBuilder(cleaned).reverse().toString());
}
```

## Mẹo Hiệu Quả
1. **Cụ Thể**: Tránh các thuật ngữ mơ hồ như "làm gì đó"
2. **Bao Gồm Ngữ Cảnh**: Đề cập đến data type, ràng buộc, hoặc yêu cầu
3. **Sử Dụng Thuật Ngữ Chuẩn**: Sử dụng các khái niệm lập trình được biết đến
4. **Đặt Vị Trí Đúng**: Đặt prompt ở nơi code cần được tạo

## Trường Hợp Sử Dụng Phổ Biến
- Tạo utility function nhanh
- Các task chuyển đổi dữ liệu
- Implementation thuật toán đơn giản
- Logic validation cơ bản
- Code configuration và setup
