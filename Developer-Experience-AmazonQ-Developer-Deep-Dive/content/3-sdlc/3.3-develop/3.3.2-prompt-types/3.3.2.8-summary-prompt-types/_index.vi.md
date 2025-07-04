---
title: "Prompt Đa Dòng"
date: 2023-08-17T00:00:00-00:00
weight: 5
chapter: false
pre: "<b>3.3.2.5 </b>"
---

# Prompt Đa Dòng

## Tổng Quan
Prompt đa dòng mở rộng beyond comment truyền thống để cung cấp hướng dẫn toàn diện cho việc tạo code phức tạp. Những prompt này có thể kéo dài nhiều dòng và bao gồm đặc tả chi tiết, ví dụ và thông tin ngữ cảnh để hướng dẫn Amazon Q Developer tạo ra các implementation tinh vi.

## Format và Cấu Trúc

### Format Prompt Có Cấu Trúc
```
Create a comprehensive user management system that includes:

1. User Registration and Authentication
   - Email/username validation
   - Password hashing with bcrypt
   - JWT token generation and validation
   - Account activation via email

2. User Profile Management
   - Profile picture upload and processing
   - Personal information CRUD operations
   - Privacy settings configuration
   - Account deletion with data retention policies

3. Security Features
   - Two-factor authentication (2FA)
   - Login attempt monitoring
   - Password reset functionality
   - Session management and timeout

Technical Requirements:
- Use TypeScript for type safety
- Implement proper error handling
- Include comprehensive unit tests
- Follow RESTful API conventions
- Document all public methods
```

## Yếu Tố Chính

### 1. Mục Tiêu Rõ Ràng
Định nghĩa những gì code cần hoàn thành ở mức độ cao.

### 2. Đặc Tả Chi Tiết
Chia nhỏ yêu cầu thành các item cụ thể, có thể thực hiện.

### 3. Ràng Buộc Kỹ Thuật
Chỉ định công nghệ, pattern hoặc quyết định kiến trúc.

### 4. Hành Vi Mong Đợi
Mô tả cách code hoạt động trong các scenario khác nhau.

### 5. Yêu Cầu Chất Lượng
Bao gồm kỳ vọng về testing, documentation và hiệu suất.

## Kỹ Thuật Prompt Nâng Cao

### 1. Prompt Dựa Trên Scenario
```
Design a real-time chat application with the following scenarios:

Scenario 1: Basic Messaging
- User joins a chat room
- Sends and receives messages in real-time
- Messages include timestamp and sender information
- Support for text formatting (bold, italic, code)

Scenario 2: Advanced Features
- File sharing with drag-and-drop
- Message reactions and threading
- User presence indicators (online/offline/typing)
- Message search and history

Scenario 3: Administrative Functions
- Room creation and moderation
- User permissions and roles
- Message deletion and editing
- Spam detection and filtering

Technical Stack:
- Frontend: React with TypeScript
- Backend: Node.js with Socket.io
- Database: MongoDB for message persistence
- Authentication: JWT with refresh tokens
```

### 2. Prompt Dựa Trên API
```
Create a REST API for an e-commerce platform with these endpoints:

Products API:
GET /api/products - List products with pagination and filtering
GET /api/products/:id - Get product details with reviews
POST /api/products - Create new product (admin only)
PUT /api/products/:id - Update product information
DELETE /api/products/:id - Soft delete product

Orders API:
POST /api/orders - Create new order with inventory validation
GET /api/orders/:id - Get order details with tracking
PUT /api/orders/:id/status - Update order status
GET /api/users/:userId/orders - Get user's order history

Implementation Requirements:
- Input validation using Joi or similar
- Rate limiting for all endpoints
- Comprehensive error responses
- API documentation with Swagger
- Unit and integration tests
```

### 3. Prompt Tập Trung Kiến Trúc
```
Implement a microservices architecture for a social media platform:

Service Breakdown:
1. User Service
   - User registration, authentication, and profile management
   - Implements OAuth2 for third-party integrations
   - Handles user relationships (following/followers)

2. Content Service
   - Post creation, editing, and deletion
   - Media upload and processing
   - Content moderation and flagging

3. Feed Service
   - Timeline generation using personalized algorithms
   - Real-time feed updates via WebSocket
   - Caching strategies for performance

4. Notification Service
   - Push notifications for mobile and web
   - Email notifications for important events
   - Notification preferences management

Cross-Cutting Concerns:
- Service discovery using Consul or similar
- API Gateway with rate limiting and authentication
- Distributed logging and monitoring
- Event-driven communication via message queues
- Database per service with eventual consistency
```

## Thực Hành Tốt cho Prompt Đa Dòng

### 1. Sử Dụng Cấu Trúc Phân Cấp
Tổ chức thông tin theo hierarchy logic với section và subsection rõ ràng.

### 2. Bao Gồm Ngữ Cảnh và Lý Do
Giải thích tại sao cần certain quyết định hoặc approach.

### 3. Cung Cấp Ví Dụ
Bao gồm sample input, output hoặc usage pattern.

### 4. Chỉ Định Yêu Cầu Non-Functional
Đề cập đến mối quan tâm về hiệu suất, bảo mật, khả năng mở rộng và maintainability.

### 5. Cân Nhắc Điểm Tích Hợp
Mô tả cách code được tạo tương tác với hệ thống hiện có.

## Ví Dụ Implementation

```typescript
/*
Create a data analytics dashboard with the following components:

Dashboard Features:
1. Real-time data visualization
   - Line charts for time series data
   - Bar charts for categorical comparisons
   - Pie charts for distribution analysis
   - Heatmaps for correlation matrices

2. Interactive Controls
   - Date range picker for filtering
   - Dropdown for metric selection
   - Search functionality for data exploration
   - Export capabilities (PDF, CSV, PNG)

3. Performance Optimization
   - Virtual scrolling for large datasets
   - Data aggregation for improved load times
   - Caching mechanisms for frequently accessed data
   - Progressive loading with skeleton screens

Technical Implementation:
- React with TypeScript for component development
- D3.js for custom visualizations
- React Query for data fetching and caching
- Material-UI for consistent design system
- Jest and React Testing Library for testing
*/

interface DashboardProps {
    userId: string;
    defaultDateRange: DateRange;
    availableMetrics: Metric[];
}

const AnalyticsDashboard: React.FC<DashboardProps> = ({
    userId,
    defaultDateRange,
    availableMetrics
}) => {
    // Implementation with all specified features
    return (
        <div className="analytics-dashboard">
            {/* Dashboard implementation */}
        </div>
    );
};
```

## Lợi Ích và Trường Hợp Sử Dụng

### Lợi Ích
- **Giải Pháp Toàn Diện**: Tạo ra implementation hoàn chình, sẵn sàng production
- **Hướng Dẫn Kiến Trúc**: Ảnh hưởng đến cấu trúc code và design pattern
- **Đảm Bảo Chất Lượng**: Bao gồm yêu cầu testing và documentation
- **Tích Hợp Ngữ Cảnh**: Alignment tốt hơn với hệ thống và standard hiện có

### Trường Hợp Sử Dụng Lý Tưởng
- Tính năng ứng dụng phức tạp
- Implementation microservice
- Thiết kế và phát triển API
- Tạo component full-stack
- Dự án tích hợp hệ thống
- Implementation pattern kiến trúc
