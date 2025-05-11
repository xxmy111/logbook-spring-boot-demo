

<!-- by 朱淼佳 -->

## 2. Feature Overview  

=======
<!-- by 朱淼佳 -->

## 2. Feature Overview  


This project provides the following core functionalities:  

### 2.1 HTTP Request & Response Logging  
**Based on Spring AOP:**  
- Create an interceptor to capture all HTTP requests and responses.  
- Log request paths, methods, parameters, and response data within the interceptor.  
- **Advantage:** Decouples business logic from logging logic, enabling flexible logging.  

**Using Spring’s `HandlerInterceptor`:**  
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
=======
  - **Advantages:** Supports high-concurrency log processing.

