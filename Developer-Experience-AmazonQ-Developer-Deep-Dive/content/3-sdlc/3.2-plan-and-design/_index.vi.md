---
title: "SDLC Phase: Plan & Design"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

Giai đoạn này tập trung vào architectural planning, design patterns research, và requirements engineering. Amazon Q Developer hỗ trợ architecture decisions, modernization strategies, và translating business requirements thành technical specifications.

{{% notice tip %}}
**Recommended Environment**: Sử dụng IDE Chat feature để duy trì consistent context trong các modules tiếp theo. AWS event participants có thể tham khảo Configuration section cho VSCode setup.
{{% /notice %}}

##### Example 1: Design Patterns Research

**Scenario**: Hiểu DDD architecture patterns cho AWS implementation

**Prompt**:
```
What are notable architecture patterns employed in Domain-Driven Design (DDD) 
and their implementation context in AWS?
```

![alt text](image.png?width=40pc)

**Key Patterns Covered**:
- **Hexagonal Architecture**: Lambda functions với ports/adapters
- **Microservices**: ECS/EKS/Lambda với bounded contexts
- **Event-Driven**: EventBridge, SNS, SQS integration
- **CQRS**: Separate read/write với DynamoDB/RDS
- **Event Sourcing**: DynamoDB Streams, Kinesis
- **Layered/Onion Architecture**: Cross-service implementation

##### Example 2: Modernization Strategy

**Scenario**: Gradual legacy modernization without big-bang approach

**Prompt**:
```
I want to avoid big-bang modernization. Instead, develop new cloud-native microservices 
alongside legacy systems while gradually replacing legacy components. 
Guide me on architecture patterns and implementation strategy.
```

**Strategic Approach**:
- **Strangler Fig Pattern**: Gradual component extraction
- **API Gateway**: Traffic routing between legacy/new systems
- **Event-Driven Architecture**: EventBridge decoupling
- **Data Migration**: Dual-write approach với DMS
- **CI/CD**: CodePipeline automation
- **Monitoring**: CloudWatch, X-Ray observability

##### Example 3: Requirements Engineering

**Context Reset**: Sử dụng `/clear` command để reset conversation context trước section này.

**3.1 Functional Requirements Analysis**

**Prompt**:
```
I need to design a microservice for online bookstore book search functionality. 
What are typical functional requirements for this use case?
```

**Core Requirements**:
- Basic/advanced search capabilities
- Relevance ranking và autocomplete
- Faceted search và full-text search
- Error handling và pagination
- Analytics và multi-language support

**3.2 User Story Translation**

**Prompt**:
```
Rephrase the functional requirements into user stories
```

**Format**: "As a [user type], I want [functionality] so that [benefit]"

**3.3 Prioritization Framework**

**Prompt**:
```
How can I help the product owner prioritize these requirements 
using a methodical weighted scoring approach?
```

**Weighted Scoring Model**:
- **Criteria**: Business value (40%), User impact (30%), Technical complexity (20%), Time to implement (10%)
- **Process**: Score 1-5, multiply by weights, rank by total scores
- **Tools**: Spreadsheets, QuickSight cho visualization

##### Example 4: User Story Development

**4.1 User Story Creation**

**Requirements**:
1. Web page captures username và displays visit count
2. Username sent to backend upon submission
3. User data stored in database với incremented count
4. Total visit count tracked và updated

**Prompt**:
```
Create user stories for website visitor and owner actors with acceptance criteria:
[Include the 4 requirements above]
```

**4.2 Behavior-Driven Development**

**Prompt**:
```
Write the user story in Gherkin format for the same requirements
```

**Gherkin Structure**:
- **Feature**: User Visit Tracking
- **Scenarios**: New user, returning user, edge cases
- **Format**: Given/When/Then/And syntax
- **Coverage**: Frontend display, backend processing, database operations

{{% notice info %}}
**BDD Value**: Gherkin scenarios phục vụ như living documentation và automated testing foundation cho development teams.
{{% /notice %}}


