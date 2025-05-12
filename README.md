
<!-- by 尤淇 -->
Logbook Spring Boot Demo Project Introduction

Logbook Spring Boot Demo is a practical open-source demonstration project meticulously crafted using Java language and Spring Boot framework, focusing on showcasing how to effectively record and comprehensively monitor HTTP requests and responses through the Logbook component.

In today's digital era, with the increasingly complex software system architecture, especially in the context of the prevailing microservices architecture, the effective recording and monitoring of HTTP communication logs have become increasingly important. The Logbook Spring Boot Demo project emerges as the right solution, acting like a precise scalpel to help developers clearly perceive every detail of HTTP requests and responses in the complex system interactions.

Project Objectives

The primary objective of this project is to become a powerful assistant for developers in integrating logging functions, providing a simple, efficient, and flexible log recording solution to significantly enhance the observability and debugging capabilities of services.

Observability Enhancement
Through detailed log records, developers can real-time grasp the running status of the system, promptly identify potential performance bottlenecks and anomalies, and thus make precise optimizations and adjustments.

Debugging Capability Enhancement
When the system encounters failures or errors, log records are like a bright lighthouse, guiding developers to quickly locate the root cause of the problem, greatly shortening the troubleshooting time and improving development efficiency.

Project Highlights

Rapid Integration
One of the remarkable advantages of the Logbook Spring Boot Demo project lies in its convenient integration method. Developers only need to perform simple configurations to easily embed the logging function into existing Spring Boot projects.

In traditional software development processes, integrating new functions often requires a great deal of time and effort, and may even require large-scale modifications and adjustments to the existing code. However, Logbook, with its simple API and good compatibility, makes this process extremely simple.

Flexible Expansion
The project supports multiple log formatting and filtering methods, allowing for personalized customization according to different business requirements.

Log Formatting
Developers can choose suitable log formats according to their own needs, such as JSON, XML, plain text, etc. The JSON format log has good readability and is easy to parse, which is convenient for subsequent data processing and analysis; while the XML format log has a wider range of applications in some specific systems.

Log Filtering
By configuring sensitive information filtering rules, the project can automatically desensitize sensitive information (such as passwords, tokens, etc.) in requests and responses, protecting user privacy and data security. At the same time, developers can also filter specific types of requests and responses according to business logic, reducing unnecessary log information, improving the readability and management efficiency of logs.

Efficiency Improvement
The Logbook Spring Boot Demo project can automatically record HTTP communication data, greatly helping developers quickly locate problems.

In today's complex distributed systems, problem troubleshooting often requires a great deal of time and effort. The traditional method of manual recording and troubleshooting is inefficient and prone to errors. Logbook can automatically collect and record HTTP communication data, including request URL, request method, request parameters, request headers, response status code, response time, etc. These rich log information provides a comprehensive perspective for developers, helping them quickly locate the root cause of the problem and improving problem-solving efficiency.

Modular Design
The project has a clear code structure and adopts a modular design concept, which is convenient for maintenance and adding new functions.

Modular design makes each functional module of the project relatively independent, reducing the coupling between modules. When modifying or expanding a certain function, only the relevant module needs to be focused on, without affecting other modules. At the same time, the modular design also makes the code structure of the project clearer, easier to understand and maintain, facilitating team member collaboration in development.

Applicable Scenarios

Recording API Call Logs in Microservices Architecture
In the microservices architecture, each service communicates with others through the HTTP protocol. The Logbook Spring Boot Demo project can help developers record detailed API call logs, including request parameters, response results, call time, and other information.

Through the analysis of API call logs, developers can understand the call relationships and call frequencies between various services, promptly discover potential performance problems and abnormal calls. At the same time, these logs can also serve as an important monitoring means for distributed systems, helping administrators promptly detect faults and abnormal situations in the system and ensure the stable operation of the system.

Debugging and Error Troubleshooting of Backend Services
In the process of developing and maintaining backend services, various errors and exceptions are inevitable. The Logbook Spring Boot Demo project can automatically record HTTP communication data, providing rich debugging information for developers.

When a problem occurs in the system, developers can quickly locate the root cause of the problem by viewing the log files. For example, if a request returns an incorrect response status code, developers can judge whether it is caused by incorrect parameters passed by the client or logical errors on the server side by viewing the request parameters and response content. This ability to quickly locate problems greatly improves the debugging efficiency of developers and shortens the problem-solving time.

Communication Audit under Data Compliance Requirements
In the context of today's data security and privacy protection, many industries have strict requirements for data compliance. The Logbook Spring Boot Demo project, through detailed recording of HTTP requests and responses, can help developers and enterprises meet data compliance requirements.

=======

<!-- by 朱淼佳 -->
## 2. Feature Overview  


This project provides the following core functionalities:  

### 2.1 HTTP Request & Response Logging  
**Based on Spring AOP:**  
- Create an interceptor to capture all HTTP requests and responses.  
- Log request paths, methods, parameters, and response data within the interceptor.  
- **Advantage:** Decouples business logic from logging logic, enabling flexible logging.  

**Using Spring’s HandlerInterceptor`:**  
- Implement the `HandlerInterceptor` interface and log requests/responses in `preHandle` and `postHandle`.  
- **Advantage:** Provides a more direct way to intercept and process HTTP requests.  

**Using Third-Party Libraries (e.g., Logbook):**  
- Integrate Logbook to automatically log HTTP request/response data.  
- Simple configuration with support for various extensions.  

### 2.2 Support for Multiple Log Formats  
**Based on Logging Frameworks (e.g., Logback or Log4j):**  
- Configure formats via `logback.xml` (Logback) or YAML/JSON (Log4j) to define different log output templates.  
- **Advantage:** Easy to use, supports multiple output formats.  

**Using Log Adapters/Converters:**  
- Implement a log adapter to convert log content into different formats (e.g., JSON, XML, or custom formats).  
- **Advantage:** Highly flexible, allowing customized output.  

**Multi-Format Log Appender:**  
- Create a custom log appender that dynamically selects log formats (e.g., JSON, plain text) based on configuration.  
- **Advantage:** Supports multiple log formats within the same system.

## 2.3 Flexible Log Filtering

- **Regular Expression-based Filtering:**
  - Use regular expressions to match URLs, request parameters, or response content for dynamic log filtering.
  - **Advantages:** More precise filtering rules, suitable for complex scenarios.

- **Dynamic Rule Engine:**
  - Integrate a rule engine (such as Drools or EasyRules) to define filtering conditions via rule files or dynamic loading.
  - **Advantages:** Supports more complex logic and combinations of conditions.

- **Distributed Filtering Rules:**
  - In distributed systems, centrally manage log filtering rules and synchronize them to all service instances.
  - **Advantages:** Unified rules, easier to maintain.

## 2.4 Dynamic Configuration Adjustment

- **Configuration Center Support:**
  - Integrate with a configuration center (such as Spring Cloud Config, Apollo, or Nacos) to dynamically load log-related configurations.
  - **Advantages:** Centralized management, supports real-time updates.

- **Database-based Configuration Updates:**
  - Store log configurations in a database and modify them in real-time through a management interface.
  - **Advantages:** Easy to operate, suitable for operations teams.

- **Hot Update Mechanism:**
  - Utilize Spring Boot’s `@ConfigurationProperties` and hot-reloading mechanism to monitor changes in configuration files and apply them in real-time.
  - **Advantages:** Simple implementation, suitable for small projects.

## 2.5 Performance Optimization

- **Batch Log Writing:**
  - Temporarily store log data in an in-memory queue and periodically write it in batches to disk or external storage.
  - **Advantages:** Reduces I/O operations, improves write efficiency.

- **Log Compression Storage:**
  - Compress log data using algorithms like GZIP when writing to log files.
  - **Advantages:** Saves storage space, suitable for large-scale log data.

## 2.6 High Extensibility

- **Support for Multiple Storage Targets:**
  - Provide interfaces to write logs to files, databases, message queues (such as Kafka, RabbitMQ), or cloud storage.
  - **Advantages:** Adapts to different storage needs.

- **Log Flow Based on Message Middleware:**
  - Send log data as messages to middleware (such as Kafka) for processing by independent services for log storage or analysis.

  - **Advantages:** Supports high-concurrency log processing.

<!-- by 莫永启 -->
## 3. Environmental requirements
To run this project, the following environmental requirements must be met:

### 3.1 Operating System
- Supports Windows, macOS, and major Linux distributions.

### 3.2 Java Runtime Environment
- It is recommended to use JDK 11 or higher.
- You can check if the JDK is installed correctly by using the following command:```bashjava -version```

### 3.3 Build Tool
- This project uses Gradle for building, and Gradle version 3.3 or higher must be installed.
- Check the Gradle version:```bashgradle -v```

### 3.4 Network Environment
- A stable internet connection is required to download dependencies and run services.
- Domestic users may need to use VPNs or other network tools due to GitHub's services located overseas.
- When running the project:```bashgradlew runDownloading https://services.gradle.org/distributions/gradle-3.3-bin.zip requires an internet connection.```---
  
<!-- by 唐文广 -->
## 4. Quick Start
Warm reminder: You need to complete the environment configuration in order to deploy this project. This project requires JDK version 1.8 or higher and Gradle version 3.3 or higher.
Follow the steps below to quickly start this project:

### 4.1 Clone the Code
First, clone the project code to your local environment:
```bash
git clone https://github.com/anyEkko/logbook-spring-boot-demo.git
```
![alt text](img/image.png)

### 4.2 Build the Project
Use Gradle to build the project:
```bash
gradlew build
```
The successful build result is shown below:
![alt text](img/gradlewbuild.png)

### 4.3 Start the Service
Run the following command to start the Spring Boot service:
```bash
gradlew bootRun
```
After the service starts successfully, it will look like this:
![alt text](img/gradlewbootRun.png)

### 4.4 Access the Service
After the project is started, it listens by default at http://localhost:8080. You can access and test it via a browser or tools like Postman.
You can access http://localhost:8080/echo/ + any test case you want.
For example: access http://localhost:8080/echo/helloworld.
You will see the text "helloworld" on the webpage.
![alt text](img/helloworld2.png)  

You can also clearly see the sample information in the backend:
![alt text](img/helloworld.png)
---

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
  - **Advantages:** Supports high-concurrency log processing.
  
<!-- by 陆发欣 -->
## 6.Configuration Description
### 6.1 Code highlighting
Visual software will highlight different keywords, values, etc. according to the syntax characteristics of YAML files. For example, "logbook", "format", "filters", etc. will be identified as keys and displayed in a specific colour, while "json", "/api/secure/*", "true", "info" and other values will be presented in another colour, which can make me We can more intuitively divide the configuration items and their corresponding values, which is easy to understand and modify.
### 6.2 intellisense
During the writing process, the Visual software will provide intelligent prompts. For example, when we enter "logbook:" and press the Enter key, the software may automatically prompt our common sub-configuration items, such as "format", "filters", etc., to help us complete the code writing quickly and accurately, and reduce the lead due to spelling errors or forgetting configuration items. To the error.
### Code Display
```logbook:
  format: json            # Log output format: json or text
  filters:
    pattern: /api/secure/*  # Filter rule: match path
    mask: true              # Mask sensitive information for matches
  log-level: info          # Log level
```
### 6.3 Structured View
Visual software usually provides a structured view panel where we can clearly see the overall structure of YAML files. For example, it can be seen that "server" and "spring" are configuration items of the same level, while "port" is a sub-item of "server", "application" is a sub-item of "spring", and "name" is " Application" sub-items, etc. This structured view can help us quickly locate a specific configuration part, which is convenient for modification and viewing.
### 6.4 Code Folding and Unfolding
Code folding and expansion: For YAML configurations with multi-level nesting, Visual software supports code folding and expansion functions. For example, we can fold the "spring" configuration item and its sub-items to display only the top-level key "spring". When we need to view or modify the "application" and "name" inside, we can expand the corresponding part. This can effectively reduce visual interference and improve the readability and maintainability of the code when processing complex YAML files.
### Code Display
```server:
  port: 8080               # Service listening port
spring:
  application:
    name: logbook-demo     # Application name
```
### 6.5 Log Configuration
• logbook: the root node of the log configuration, including all log-related settings.
• format: Set the log output format to JSON, which is convenient for program analysis and integration with other systems.
• filters: define filter rules, including path matching and sensitive information shielding.
• pattern: The matching path is /api/secure/*, which means that all paths starting with /api/secure/ will be filtered.
• mask: set to true to shield the sensitive information in the matching path.
• log-level: Set the log level to info, and record log information above the info level.
### Code Display
```logbook:
  format: json            # Log output format: json or text
  filters:
    pattern: /api/secure/*  # Filter rule: match path
    mask: true              # Mask sensitive information for matches
  log-level: info          # Log level
```
### 6.6 Service and application configuration
• server: service monitoring configuration.
• port: Set the service listening port to 8080, which is used to receive client requests.
• spring: Spring framework-related configuration.
• application: application configuration.
• name: Set the application name to logbook-demo, which is used to identify and manage applications in the Spring ecosystem.
Advantages of using Visual software
When writing and managing YAML files in Visual software (such as Visual Studio Code), you can make full use of the following functions:
1. Code highlighting: Different configuration items and values are displayed in different colours for easy distinction and understanding.
2. Intelligent Tips: Automatically prompt common configuration items and values to reduce manual input errors.
3. Structured view: provides an overview of the file structure, which is convenient to quickly locate specific configuration items.
4. Code folding: supports folding and expanding nested configurations to improve code readability.
Through these functions, the writing and maintenance of YAML configuration files can be completed efficiently and accurately to ensure that the configuration meets business needs.
### Code Display
```server:
  port: 8080               # Service listening port
spring:
  application:
    name: logbook-demo     # Application name

```

<!--by 谢鹏飞-->
### 7. Testing Methods
- This project includes various testing methods to ensure the correctness and stability of its functions:
### 7.1 JUnit Unit Testing
- This project is a Gradle-based project.
- Unit tests covering core functionalities are written using JUnit.
- Dependencies are added in the build.gradle file.
- JUnit 4 dependency:
- dependencies {
- testImplementation 'junit:junit:4.13.2'
- }
- There are two ways to run tests:
- Run the following command to execute all test methods:
- bash
- gradle test
- Run a specific test method:
- Locate the package and method of the class.
- Example:
- gradle test --tests "com.example.LogbookSpringBootDemoApplicationTest.testAdd"

### 7.2 Interface Testing
### 7.2.1 Testing with Postman
- Postman is a powerful API testing tool that supports sending various types of HTTP requests and viewing responses.
- Open the Postman application.
- Create a GET request or other types of requests (e.g., GET, POST, PUT, DELETE).
- Example request:
- Execute a GET request in the project.
- Enter the URL: http://localhost:8080/echo/{message}
- Replace {message} with the desired message.
- Click the Send button to send the request.
- After a successful Send, you can view the response data.
- Verify whether the response data meets the expectations.

### 7.2.2 Testing with Swagger Documentation
- Add dependencies in the build.gradle file:
- dependencies {
- implementation 'org.springdoc:springdoc-openapi-ui:1.6.11'
- }
- After starting the project, the Swagger documentation will be automatically generated.
- Access the Swagger UI page via the browser at the URL: http://localhost:8080/swagger-ui.html
- Select the interface to be tested, fill in the parameters, and click the Try it out button to send the request.
- Example request:
- Enter the URL: http://localhost:8080/echo/{message}
- Replace {message} with the desired message.
- After sending the request, you can view the response information.
- Verify whether the response data meets the expectations.
- Advantages of Swagger documentation testing:
- Compared to Postman, it allows direct interface testing in the browser.


=======
