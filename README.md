Logbook Spring Boot Starter demo
================================

This is a simple Spring Boot application to test 1.1.1 version of Zalando's Logbook Spring Boot Starter.

The problem in test is the exception thrown when trying to access `/favicon.ico` path.

<!-- by 伍师杰 -->
### 5. 
Project ArchitectureThis project adopts a modular architecture design, following the principles of high cohesion and low coupling to ensure the system's maintainability and scalability. The architecture is mainly divided into the following core modules:

### 5.1
Logging ModuleImplementation: 

Full link interception and logging of HTTP requests/responses based on the Logbook framework.Core Functions:
- Support for multiple log format configurations such as JSON and text.
- Provide refined filtering rules for request/response content.
- Support asynchronous log writing to avoid blocking the main business process.
- Extendable log output channels (files, ELK, databases, etc.).

### 5.2 
Configuration ModuleImplementation: 

Based on the Spring Boot configuration system, combined with Nacos for dynamic configuration.Core Functions:
- Centrally manage application configurations via application.yml.
- Support multi-environment configuration isolation (dev/test/prod).
- Implement hot configuration update mechanism, with key parameter modifications taking effect in real-time.
- Provide configuration version management and rollback capabilities.

### 5.3 Security ModuleImplementation: 
Based on custom filters and annotations for sensitive data processing.Core Functions:
- Automatically identify and mask sensitive information such as ID numbers and phone numbers.- Support custom desensitization rules with regular expressions.
- Provide logging audit and tracking capabilities.
- Comply with data security regulations such as GDPR.

### 5.4 Controller ModuleImplementation: 
Spring MVC RESTful style API design.Core Functions:
- Clear API version management (/v1/api/...).
- Unified exception handling mechanism.- Complete Swagger API documentation.
- Automatic validation of request parameters (JSR-303).Module Interaction Design:
- Each module interacts through clearly defined interface contracts: 
- Achieve module decoupling through Dependency Injection (DI).
- Set circuit breaker downgrade mechanisms at critical interaction points.  
- Use DTO objects for communication between modules.
- Implement asynchronous event notification through Spring Event.This architecture design supports horizontal scaling. Subsequent enhancements can be achieved through:
- Introducing a modular loading mechanism (OSGi).
- Adding gRPC internal communication protocols.
- Supporting plugin-based functionality extensions.