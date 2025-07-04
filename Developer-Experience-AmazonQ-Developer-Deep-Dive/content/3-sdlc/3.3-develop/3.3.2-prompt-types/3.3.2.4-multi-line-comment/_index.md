---
title: "Multi Line Comment"
date: 2023-08-17T00:00:00-00:00
weight: 4
chapter: false
pre: "<b>3.3.2.4 </b>"
---

# Multi Line Comment Prompts

## Overview
Multi-line comment prompts provide detailed instructions using block comments to generate complex code implementations. These prompts allow for comprehensive descriptions, specifications, and context that result in more sophisticated code generation.

## Structure and Format

### Python/Java Style
```python
"""
Create a class to manage user authentication
- Include methods for login, logout, and password reset
- Implement session management with token-based authentication
- Add input validation and error handling
- Support both email and username login
"""
```

### JavaScript/C++ Style
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

## Key Components

### 1. Primary Objective
Clearly state the main goal of the code to be generated.

### 2. Detailed Requirements
List specific features, methods, or functionality needed.

### 3. Technical Specifications
Include data structures, algorithms, or patterns to use.

### 4. Constraints and Considerations
Mention performance, security, or compatibility requirements.

## Best Practices

### 1. Use Structured Format
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

### 2. Include Examples and Expected Behavior
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

## Example Implementations

### Complex Class Generation
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

### Algorithm Implementation
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

## Advanced Techniques

### 1. Context-Aware Prompts
Include information about existing codebase, dependencies, and integration points.

### 2. Performance Specifications
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

### 3. Design Pattern Integration
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

## Benefits of Multi-Line Comments
- **Comprehensive Specifications**: Detailed requirements lead to better code generation
- **Complex Logic**: Suitable for generating sophisticated algorithms and systems
- **Documentation Integration**: Generated code often includes inline documentation
- **Architectural Guidance**: Can specify design patterns and code organization

## When to Use Multi-Line Comments
- Complex class or module creation
- Algorithm implementations with specific requirements
- Integration with existing systems
- Code that requires detailed documentation
- Multiple interconnected functions or methods
