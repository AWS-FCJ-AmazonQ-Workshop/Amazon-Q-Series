---
title: "Comment Đa Dòng"
date: 2023-08-17T00:00:00-00:00
weight: 4
chapter: false
pre: "<b>3.3.2.4 </b>"
---

# Prompt Comment Đa Dòng

## Tổng Quan
Prompt comment đa dòng cung cấp hướng dẫn chi tiết sử dụng block comment để tạo ra các implementation code phức tạp. Những prompt này cho phép mô tả toàn diện, đặc tả và ngữ cảnh dẫn đến việc tạo code tinh vi hơn.

## Cấu Trúc và Format

### Kiểu Python/Java
```python
"""
Create a class to manage user authentication
- Include methods for login, logout, and password reset
- Implement session management with token-based authentication
- Add input validation and error handling
- Support both email and username login
"""
```

### Kiểu JavaScript/C++
```javascript
/*
Implement a shopping cart system with:
- Add/remove items functionality
- Calculate total price with tax
- Apply discount codes
- Handle inventory validation
- Persist cart state in localStorage
*/
```

## Thành Phần Chính

### 1. Mục Tiêu Chính
Nêu rõ mục tiêu chính của code cần được tạo.

### 2. Yêu Cầu Chi Tiết
Liệt kê các tính năng, method hoặc functionality cụ thể cần thiết.

### 3. Đặc Tả Kỹ Thuật
Bao gồm data structure, thuật toán hoặc pattern cần sử dụng.

### 4. Ràng Buộc và Cân Nhắc
Đề cập đến yêu cầu về hiệu suất, bảo mật hoặc tương thích.

## Thực Hành Tốt

### 1. Sử Dụng Format Có Cấu Trúc
```python
"""
Objective: Create a data validation utility class

Requirements:
- Validate email addresses using regex
- Check password strength (length, complexity)
- Sanitize user input to prevent XSS
- Support custom validation rules

Implementation Notes:
- Use static methods for validation functions
- Return detailed error messages
- Include unit test examples
"""
```

### 2. Bao Gồm Ví Dụ và Hành Vi Mong Đợi
```javascript
/*
Create a rate limiting middleware for Express.js

Functionality:
- Limit requests per IP address
- Configurable time windows (per minute/hour)
- Different limits for different endpoints
- Redis backend for distributed systems

Example Usage:
app.use(rateLimit({ windowMs: 60000, max: 100 }))

Expected Behavior:
- Return 429 status when limit exceeded
- Include reset time in response headers
*/
```

## Ví Dụ Implementation

### Tạo Class Phức Tạp
```python
"""
Create a file manager class with async operations:
- Upload files with progress tracking
- Download files with resume capability
- File compression and decompression
- Metadata extraction and storage
- Support for multiple cloud storage providers
"""

class FileManager:
    def __init__(self, storage_provider='local'):
        self.storage_provider = storage_provider
        self.upload_progress = {}
    
    async def upload_file(self, file_path, destination):
        # Implementation with progress tracking
        pass
    
    async def download_file(self, source, destination, resume=True):
        # Implementation with resume capability
        pass
    
    def compress_file(self, file_path, compression_type='zip'):
        # File compression implementation
        pass
```

### Implementation Thuật Toán
```java
/*
Implement a graph traversal system:
- Support both DFS and BFS algorithms
- Handle weighted and unweighted graphs
- Find shortest paths using Dijkstra's algorithm
- Detect cycles in directed graphs
- Provide visualization data for graph rendering
*/

public class GraphTraversal {
    private Map<Integer, List<Edge>> adjacencyList;
    
    public GraphTraversal() {
        this.adjacencyList = new HashMap<>();
    }
    
    public List<Integer> depthFirstSearch(int startNode) {
        // DFS implementation
    }
    
    public List<Integer> breadthFirstSearch(int startNode) {
        // BFS implementation
    }
}
```

## Kỹ Thuật Nâng Cao

### 1. Prompt Nhận Thức Ngữ Cảnh
Bao gồm thông tin về codebase hiện có, dependency và điểm tích hợp.

### 2. Đặc Tả Hiệu Suất
```python
"""
Create a caching layer with the following requirements:
- Memory usage under 100MB
- Sub-millisecond read operations
- LRU eviction policy
- Thread-safe operations
- Configurable TTL per cache entry
"""
```

### 3. Tích Hợp Design Pattern
```javascript
/*
Implement Observer pattern for event management:
- Support multiple event types
- Async event handlers
- Priority-based event processing
- Event filtering and transformation
- Integration with existing EventEmitter
*/
```

## Lợi Ích của Comment Đa Dòng
- **Đặc Tả Toàn Diện**: Yêu cầu chi tiết dẫn đến việc tạo code tốt hơn
- **Logic Phức Tạp**: Phù hợp để tạo thuật toán và hệ thống tinh vi
- **Tích Hợp Documentation**: Code được tạo thường bao gồm inline documentation
- **Hướng Dẫn Kiến Trúc**: Có thể chỉ định design pattern và tổ chức code

## Khi Nào Sử Dụng Comment Đa Dòng
- Tạo class hoặc module phức tạp
- Implementation thuật toán với yêu cầu cụ thể
- Tích hợp với hệ thống hiện có
- Code cần documentation chi tiết
- Nhiều function hoặc method liên kết với nhau
