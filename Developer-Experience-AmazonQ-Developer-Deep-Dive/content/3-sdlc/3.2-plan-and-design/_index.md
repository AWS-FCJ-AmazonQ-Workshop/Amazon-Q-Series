---
title: "SDLC Phase: Plan and Design"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

This phase focuses on architectural planning, design patterns research, and requirements engineering. Amazon Q Developer assists with architecture decisions, modernization strategies, and translating business requirements into technical specifications.

{{% notice tip %}}
**Recommended Environment**: Use IDE Chat feature for consistent context throughout subsequent modules. AWS event participants can reference Configuration section for VSCode setup.
{{% /notice %}}

##### Example 1: Design Patterns Research

**Scenario**: Understanding DDD architecture patterns for AWS implementation

**Prompt**:
```
What are notable architecture patterns employed in Domain-Driven Design (DDD) 
and their implementation context in AWS?
```

![alt text](image.png?width=40pc)

**Key Patterns Covered**:
- **Hexagonal Architecture**: Lambda functions with ports/adapters
- **Microservices**: ECS/EKS/Lambda with bounded contexts
- **Event-Driven**: EventBridge, SNS, SQS integration
- **CQRS**: Separate read/write with DynamoDB/RDS
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
- **Data Migration**: Dual-write approach with DMS
- **CI/CD**: CodePipeline automation
- **Monitoring**: CloudWatch, X-Ray observability

##### Example 3: Requirements Engineering

**Context Reset**: Use `/clear` command to reset conversation context before this section.

**3.1 Functional Requirements Analysis**

**Prompt**:
```
I need to design a microservice for online bookstore book search functionality. 
What are typical functional requirements for this use case?
```

**Core Requirements**:
- Basic/advanced search capabilities
- Relevance ranking and autocomplete
- Faceted search and full-text search
- Error handling and pagination
- Analytics and multi-language support

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
- **Tools**: Spreadsheets, QuickSight for visualization

##### Example 4: User Story Development

**4.1 User Story Creation**

**Requirements**:
1. Web page captures username and displays visit count
2. Username sent to backend upon submission
3. User data stored in database with incremented count
4. Total visit count tracked and updated

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
**BDD Value**: Gherkin scenarios serve as living documentation and automated testing foundation for development teams.
{{% /notice %}}