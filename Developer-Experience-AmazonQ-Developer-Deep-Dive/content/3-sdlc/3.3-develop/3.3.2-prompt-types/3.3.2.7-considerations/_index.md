---
title: "Multi Line Prompt"
date: 2023-08-17T00:00:00-00:00
weight: 5
chapter: false
pre: "<b>3.3.2.5 </b>"
---

# Multi Line Prompt

## Overview
Multi-line prompts extend beyond traditional comments to provide comprehensive instructions for complex code generation. These prompts can span multiple lines and include detailed specifications, examples, and contextual information to guide Amazon Q Developer in creating sophisticated implementations.

## Format and Structure

### Structured Prompt Format
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

## Key Elements

### 1. Clear Objectives
Define what the code should accomplish at a high level.

### 2. Detailed Specifications
Break down requirements into specific, actionable items.

### 3. Technical Constraints
Specify technologies, patterns, or architectural decisions.

### 4. Expected Behaviors
Describe how the code should function in different scenarios.

### 5. Quality Requirements
Include testing, documentation, and performance expectations.

## Advanced Prompt Techniques

### 1. Scenario-Based Prompts
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

### 2. API-Driven Prompts
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

### 3. Architecture-Focused Prompts
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

## Best Practices for Multi-Line Prompts

### 1. Use Hierarchical Structure
Organize information in a logical hierarchy with clear sections and subsections.

### 2. Include Context and Rationale
Explain why certain decisions or approaches are needed.

### 3. Provide Examples
Include sample inputs, outputs, or usage patterns.

### 4. Specify Non-Functional Requirements
Address performance, security, scalability, and maintainability concerns.

### 5. Consider Integration Points
Describe how the generated code should interact with existing systems.

## Example Implementation

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

## Benefits and Use Cases

### Benefits
- **Comprehensive Solutions**: Generate complete, production-ready implementations
- **Architectural Guidance**: Influence code structure and design patterns
- **Quality Assurance**: Include testing and documentation requirements
- **Context Integration**: Better alignment with existing systems and standards

### Ideal Use Cases
- Complex application features
- Microservice implementations
- API design and development
- Full-stack component creation
- System integration projects
- Architecture pattern implementations
