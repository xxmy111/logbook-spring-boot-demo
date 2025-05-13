

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

<!-- by 莫永启 -->
## 3. Environmental requirements
To run this project, the following environmental requirements must be met:

# 3.1 Operating System
This system supports mainstream operating system platforms. The specific compatibility details are as follows:

### 3.1.1 Windows System
- **Supported Versions**: Windows 10 (1903 or later updates), Windows 11 (all editions)
- **Environment Requirements**: 64-bit operating system must be enabled. It is recommended to disable real-time antivirus scanning (to avoid interfering with the build process).
- **Special Configuration**: It is recommended to use the Windows Subsystem for Linux (WSL2) environment for development and debugging. This can be installed via **Control Panel → Programs and Features → Turn Windows features on or off**.

### 3.1.2 macOS System
- **Supported Versions**: macOS Catalina (10.15) or later
- **Environment Configuration**: Xcode Command Line Tools must be installed (run `xcode-select --install` in the terminal).
- **Permission Settings**: It is recommended to set read and write permissions for the project directory (`chmod -R 755 project_dir`).

### 3.1.3 Linux Distributions
- **Mainstream Support**: Ubuntu 20.04 LTS/22.04 LTS, Debian 11+/12+, CentOS 8+/Rocky Linux 8+, Fedora 34+
- **Dependency Installation**:
  ```bash
  # Ubuntu/Debian Systems
  sudo apt-get install build-essential unzip curl

  # CentOS/Rocky Linux Systems
  sudo dnf groupinstall "Development Tools"
  sudo dnf install unzip curl
  ```
- **Kernel Requirement**: It is recommended to use kernel version 5.4 or higher (check with `uname -r`).

# 3.2 Java Runtime Environment

### 3.2.1 Version Requirements
- It is recommended to use **Java Development Kit (JDK) 11 or higher**, with long-term support (LTS) versions (such as OpenJDK 11/17/21) being preferred.

**Version Comparison**:
| Version    | Support Period      | Key Features               | Recommended Scenarios |
|------------|---------------------|----------------------------|-----------------------|
| JDK 11 LTS | Until September 2026 | HTTP/2 support, ZGC garbage collection | Production deployments |
| JDK 17 LTS | Until September 2029 | Sealed classes, virtual threads | Development with new features |

### 3.2.2 Installation and Verification
- **Installation Guide**:
  - **Official Download**: Obtain the appropriate package from the [Java Official Website](https://www.oracle.com/java/technologies/downloads/) or [OpenJDK Official Website](https://adoptium.net/).
  - **Package Manager Installation**:
    ```bash
    # Ubuntu Systems
    sudo apt install openjdk-11-jdk

    # macOS Systems (Homebrew)
    brew install openjdk@11
    ```
- **Verification Method**:
  ```bash
  java -version
  # Example of correct output: openjdk 11.0.19 2023-10-17
  ```
- **Environment Configuration**:
  - The JDK installation path must be added to the system PATH variable (e.g., configure in **Advanced System Settings → Environment Variables** for Windows systems).
  - It is recommended to specify the JDK path via the `JAVA_HOME` environment variable (for recognition by build tools).

# 3.3 Build Tool

### 3.3.1 Gradle Environment Requirements
- **Version Requirement**: Gradle 3.3 or higher must be installed. Version 7.0+ is recommended for optimal performance.
- **Feature Advantages**:
  - Flexible build scripts based on Groovy/Kotlin DSL
  - Incremental Build support for improved compilation efficiency
  - Built-in dependency management system (supports Maven/Gradle repositories)

### 3.3.2 Installation and Upgrade
- **Manual Installation**:
  - **Download Location**: [Gradle Official Download Page](https://gradle.org/releases/)
  - **Installation Steps**:
    ```bash
    # Unzip the installation package
    unzip gradle-7.6-bin.zip -d /opt/gradle

    # Configure environment variables
    echo "export PATH=/opt/gradle/gradle-7.6/bin:\$PATH" >> ~/.bashrc
    source ~/.bashrc
    ```
- **Version Check**:
  ```bash
  gradle -v
  # The correct output should include the Gradle version and JVM information
  ```
- **Gradle Wrapper Usage**:
  - The project includes Gradle Wrapper scripts (`gradlew`/`gradlew.bat`). Use these scripts preferentially.
  - The first run will automatically download the Gradle version specified by the project (3.3+) to the local cache (`~/.gradle/wrapper/dists/`).
  - **Advantages**: Avoid manual Gradle version management and ensure team environment consistency.

# 3.4 Network Environment

### 3.4.1 Basic Network Requirements
- **Connection Requirements**: A stable internet connection of 100 Mbps or higher is required. A wired network is recommended for dependency downloads.
- **Port Requirements**: Ports 80 (HTTP), 443 (HTTPS), and 8081 (Gradle repository proxy) must be open.

### 3.4.2 Optimization for Domestic Environments
- **GitHub Access**:
  - Due to GitHub servers being located overseas, access from China may experience latency or connectivity issues.
  - **Solutions**:
    - Use legal network acceleration tools (complying with relevant laws and regulations).
    - Configure Git proxy:
      ```bash
      git config --global http.proxy http://127.0.0.1:1080
      git config --global https.proxy https://127.0.0.1:1080
      ```
- **Dependency Download Acceleration**:
  - Configure domestic mirror sources (add to `build.gradle` or `settings.gradle`):
    ```groovy
    repositories {
        maven { url 'https://maven.aliyun.com/repository/public' }
        mavenCentral()
    }
    ```
- **Gradle Wrapper Optimization**:
  ```bash
  # Manually download the Gradle distribution to local
  wget https://services.gradle.org/distributions/gradle-3.3-bin.zip -P ~/.gradle/wrapper/dists/
  ```

### 3.4.3 Offline Environment Configuration
For environments without internet access, the following must be downloaded in advance:
- The corresponding Gradle distribution version (placed in the `gradle/wrapper/` directory).
- All JAR dependencies required by the project (cached via `gradle offline --configuration compileClasspath`).
**Offline Execution Command**:./gradlew run --offline
  

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
