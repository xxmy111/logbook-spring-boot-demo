
<!--by 尤淇-->
项目简介
Logbook Spring Boot Demo 是一个采用 Java 语言和 Spring Boot 框架精心打造的实用型开源演示项目，专注于展示如何巧妙地通过 Logbook 组件实现 HTTP 请求与响应日志的高效记录与全面监控。

在当今数字化时代，随着软件系统架构日益复杂，尤其是在微服务架构盛行的背景下，对 HTTP 通信日志的有效记录和监控变得愈发重要。Logbook Spring Boot Demo 项目应运而生，它犹如一把精准的手术刀，帮助开发者在纷繁复杂的系统交互中，清晰地洞察 HTTP 请求和响应的每一个细节。

项目目标
项目的主要目标是成为开发者集成日志功能的得力助手，通过提供简单、高效且灵活的日志记录解决方案，显著提高服务的可观测性和调试能力。

​​可观测性提升​​：通过详细的日志记录，开发者能够实时掌握系统的运行状态，及时发现潜在的性能瓶颈和异常情况，从而做出精准的优化和调整。
​​调试能力增强​​：当系统出现故障或错误时，日志记录就像一座明亮的灯塔，引导开发者快速定位问题根源，大大缩短排查时间，提高开发效率。
二、项目亮点
快速集成
Logbook Spring Boot Demo 项目的一大显著优势在于其便捷的集成方式。开发者只需进行简单配置，即可轻松将日志功能嵌入现有的 Spring Boot 项目中。

在传统的软件开发过程中，集成新的功能往往需要耗费大量的时间和精力，甚至可能需要对现有代码进行大规模的修改和调整。然而，Logbook 凭借其简洁的 API 和良好的兼容性，使得这一过程变得异常简单。

灵活扩展
项目支持多种日志格式化和过滤方式，能够根据不同的业务需求进行个性化定制。

​​日志格式化​​：开发者可以根据自身需求，选择适合的日志格式，如 JSON、XML、纯文本等。JSON 格式的日志具有良好的可读性和便于解析的特点，方便后续的数据处理和分析；而 XML 格式的日志则在某些特定的系统中具有更广泛的应用。
​​日志过滤​​：通过配置敏感信息过滤规则，项目能够自动对请求和响应中的敏感信息（如密码、Token 等）进行脱敏处理，保护用户隐私和数据安全。同时，开发者还可以根据业务逻辑，对特定类型的请求和响应进行筛选，减少不必要的日志信息，提高日志的可读性和管理效率。
提升效率
Logbook Spring Boot Demo 项目能够自动记录 HTTP 通信数据，极大地帮助开发者快速定位问题。

在当今复杂的分布式系统中，问题的排查往往需要耗费大量的时间和精力。传统的通过人工记录和排查的方式效率低下，容易出错。而 Logbook 能够自动收集和记录 HTTP 通信数据，包括请求的 URL、请求方法、请求参数、请求头、响应状态码、响应时间等信息。这些丰富的日志信息为开发者提供了全方位的视角，能够帮助他们快速定位问题的根源，提高问题解决的效率。

模块化设计
项目的代码结构清晰，采用了模块化设计理念，便于维护和添加新功能。

模块化设计使得项目的各个功能模块相对独立，降低了模块之间的耦合度。当需要对某个功能进行修改或扩展时，只需要关注相关的模块，而不会对其他模块产生影响。同时，模块化的设计也使得项目的代码结构更加清晰，易于理解和维护，方便团队成员之间的协作开发。

三、适用场景
微服务架构中记录 API 调用日志
在微服务架构中，各个服务之间通过 HTTP 协议进行通信。Logbook Spring Boot Demo 项目可以帮助开发者详细记录 API 调用的日志，包括请求的参数、响应的结果、调用的时间等信息。

通过对 API 调用日志的分析，开发者可以了解各个服务之间的调用关系和调用频率，及时发现潜在的性能问题和异常调用。同时，这些日志还可以作为分布式系统的一个重要的监控手段，帮助管理员及时发现系统中的故障和异常情况，保障系统的稳定运行。

后端服务的调试与错误排查
在开发和维护后端服务的过程中，难免会遇到各种错误和异常情况。Logbook Spring Boot Demo 项目能够自动记录 HTTP 通信数据，为开发者提供了丰富的调试信息。

当系统出现问题时，开发者可以通过查看日志文件，快速定位问题的根源。例如，如果一个请求返回了错误的响应状态码，开发者可以通过查看请求的参数和响应的内容，判断是由于客户端传递的参数错误还是服务端的逻辑错误导致的。这种快速定位问题的能力，大大提高了开发者的调试效率，缩短了问题的解决时间。

数据合规需求下的通信审计
在当今数据安全和隐私保护的背景下，许多行业都对数据的合规性有着严格的要求。Logbook Spring Boot Demo 项目通过对 HTTP 请求和响应的详细记录，能够帮助开发者和企业满足数据合规的需求。



<!-- by 朱淼佳 -->
=======



=======
## 2. 功能特性

本项目提供以下核心功能：

### 2.1 HTTP 请求与响应日志记录
- 基于 Spring AOP，创建一个拦截器，拦截所有的 HTTP 请求和响应。
- 在拦截器中记录请求的路径、方法、参数和响应数据。
- 优点：解耦业务代码和日志逻辑，实现灵活的日志记录。

- 使用 Spring 的 HandlerInterceptor：
- 实现 HandlerInterceptor 接口，在 preHandle 和 postHandle 方法中记录请求和响应。
- 优点：提供了更直接的方式来拦截和处理 HTTP 请求。

- 使用第三方库（如 Logbook）：
- 直接集成 Logbook，它能够自动记录 HTTP 请求和响应数据。
- 配置简单，支持多种扩展。

### 2.2 支持多种日志格式
- 基于日志框架（如 Logback 或 Log4j）配置格式：
- 通过 Logback 的配置文件（logback.xml）或 Log4j 的 YAML/JSON 配置文件，定义不同格式的日志输出模板。
- 优点：简单易用，支持多种输出格式。

- 使用日志适配器/转换器：
- 实现一个日志适配器，将日志内容转换为不同格式（如 JSON、XML 或自定义格式）。
- 优点：灵活性高，可根据需求定制输出。

- 多格式日志输出器：
- 创建一个自定义的日志输出器，根据配置动态选择日志格式（如 JSON、纯文本等）。
- 优点：支持在同一系统中同时输出不同格式的日志。

## 2.3 灵活的日志过滤
- 基于正则表达式的过滤：
- 使用正则表达式匹配 URL、请求参数或响应内容，动态过滤日志。
- 优点：更精确的过滤规则，适合复杂场景。
- 动态规则引擎：

- 集成规则引擎（如 Drools 或 EasyRules），支持以规则文件或动态加载的方式定义过滤条件。
- 优点：支持更复杂的逻辑和条件组合。

- 分布式过滤规则：
- 在分布式系统中，集中管理日志过滤规则，并同步到各服务实例。
- 优点：统一规则，便于维护。

##  2.4 配置动态调整
- 配置中心支持：
- 集成配置中心（如 Spring Cloud Config、Apollo 或 Nacos），动态加载日志相关配置。
- 优点：集中化管理，支持实时更新。

- 基于数据库的配置更新：
- 将日志配置存储在数据库中，通过管理界面实时修改和生效。
- 优点：易于操作，适合运维团队使用。

- 热点更新机制：
- 利用 Spring Boot 的 @ConfigurationProperties 和热加载机制，监听配置文件的变化并实时生效。
- 优点：实现简单，适合小型项目。

##  2.5 性能优化
- 日志批量写入：
- 将日志数据暂存到内存队列中，定期批量写入磁盘或外部存储。
- 优点：减少 I/O 操作，提高写入效率。

- 日志压缩存储：
- 在写入日志文件时，使用 GZIP 等压缩算法对数据进行压缩。
- 优点：节省存储空间，适合大规模日志数据。

##  2.6 扩展性强
- 支持多种存储目标：
- 提供接口支持，将日志写入文件、数据库、消息队列（如 Kafka、RabbitMQ）或云存储。
- 优点：适应不同的存储需求。

- 基于消息中间件的日志流转：
- 将日志数据作为消息发送到中间件（如 Kafka），再由独立服务处理日志存储或分析。

- 优点：支持高并发日志处理。


<!-- by 莫永启 -->
## 3. 环境要求

运行本项目需要满足以下环境要求：

### 3.1 操作系统
本系统支持主流操作系统平台，具体兼容性说明如下：
#### 3.1.1 Windows 系统
- **支持版本**：Windows 10（1903 及以上更新）、Windows 11 全系列
- **环境要求**：需启用 64 位操作系统，建议关闭防病毒软件实时扫描（避免干扰构建过程）
- **特殊配置**：推荐使用 Windows Subsystem for Linux (WSL2) 环境进行开发调试，可通过控制面板→程序和功能→启用或关闭 Windows 功能进行安装

#### 3.1.2 macOS 系统
- **支持版本**：macOS Catalina (10.15) 及以上
- **环境配置**：需安装 Xcode Command Line Tools（通过终端运行 `xcode-select --install` 安装）
- **权限说明**：建议为项目目录设置读写权限（`chmod -R 755 project_dir`）

#### 3.1.3 Linux 发行版
- **主流支持**：Ubuntu 20.04 LTS/22.04 LTS、Debian 11+/12+、CentOS 8+/Rocky Linux 8+、Fedora 34+
- **依赖安装**：
  ```bash
  # Ubuntu/Debian 系统
  sudo apt-get install build-essential unzip curl

  # CentOS/Rocky Linux 系统
  sudo dnf groupinstall "Development Tools"
  sudo dnf install unzip curl
  ```
- **内核要求**：建议使用 5.4 及以上内核版本（通过 `uname -r` 查看）

### 3.2 Java 运行环境
#### 3.2.1 版本要求
推荐使用 Java Development Kit (JDK) 11 或更高版本，优先选择长期支持 (LTS) 版本（如 OpenJDK 11/17/21）

**版本对比**：
| 版本       | 支持周期       | 特性亮点                  | 推荐场景         |
|------------|----------------|---------------------------|------------------|
| JDK 11 LTS | 至 2026 年 9 月 | HTTP/2 支持、ZGC 垃圾回收 | 生产环境部署     |
| JDK 17 LTS | 至 2029 年 9 月 | 密封类、虚拟线程          | 新特性开发       |

#### 3.2.2 安装验证
- **安装指引**：
  - **官方下载**：通过 [Java 官网](https://www.oracle.com/java/technologies/downloads/) 或 [OpenJDK 官网](https://adoptium.net/) 获取对应平台安装包
  - **包管理安装**：
    ```bash
    # Ubuntu 系统
    sudo apt install openjdk-11-jdk

    # macOS 系统（Homebrew）
    brew install openjdk@11
    ```
- **验证方法**：
  ```bash
  java -version
  # 正确输出示例：openjdk 11.0.19 2023-10-17
  ```
- **环境配置**：
  - 需将 JDK 安装路径加入系统 PATH 变量（例如 Windows 系统在高级系统设置→环境变量中配置）
  - 建议通过 `JAVA_HOME` 环境变量指定 JDK 路径（用于构建工具识别）

### 3.3 构建工具
#### 3.3.1 Gradle 环境要求
- **版本要求**：需安装 Gradle 3.3 及以上版本，推荐使用 7.0+ 版本以获得最佳性能
- **特性优势**：
  - 基于 Groovy/Kotlin DSL 的灵活构建脚本
  - 支持增量构建（Incremental Build）提升编译效率
  - 内置依赖管理系统（支持 Maven/Gradle 仓库）

#### 3.3.2 安装与升级
- **手动安装**：
  - **下载地址**：[Gradle 官方下载页](https://gradle.org/releases/)
  - **安装步骤**：
    ```bash
    # 解压安装包
    unzip gradle-7.6-bin.zip -d /opt/gradle
    # 配置环境变量
    echo "export PATH=/opt/gradle/gradle-7.6/bin:\$PATH" >> ~/.bashrc
    source ~/.bashrc
    ```
- **版本检查**：
  ```bash
  gradle -v
  # 正确输出应包含 Gradle 版本号及 JVM 信息
  ```
- **Gradle Wrapper 使用**：
  - 项目已包含 Gradle Wrapper 脚本（`gradlew`/`gradlew.bat`），优先使用该脚本运行
  - 首次运行时会自动下载项目指定的 Gradle 版本（3.3+）到本地缓存（`~/.gradle/wrapper/dists/`）
  - **优势**：避免手动管理 Gradle 版本，确保团队环境一致性

### 3.4 网络环境
#### 3.4.1 基础网络要求
- **连接要求**：需具备 100Mbps 以上稳定互联网连接，建议使用有线网络进行依赖下载
- **端口需求**：需开放 80（HTTP）、443（HTTPS）、8081（Gradle 仓库代理）端口

#### 3.4.2 国内环境优化
- **GitHub 访问**：
  - 由于 GitHub 服务器位于境外，国内访问可能存在延迟或连接问题
  - **解决方案**：
    - 使用合法的网络加速工具（需遵守相关法律法规）
    - 配置 Git 代理：
      ```bash
      git config --global http.proxy http://127.0.0.1:1080
      git config --global https.proxy https://127.0.0.1:1080
      ```
- **依赖下载加速**：
  - 配置国内镜像源（在 `build.gradle` 或 `settings.gradle` 中添加）：
    ```groovy
    repositories {
        maven { url 'https://maven.aliyun.com/repository/public' }
        mavenCentral()
    }
    ```
- **Gradle Wrapper 优化**：
  ```bash
  # 手动下载 Gradle 发行版到本地
  wget https://services.gradle.org/distributions/gradle-3.3-bin.zip -P ~/.gradle/wrapper/dists/
  ```

#### 3.4.3 离线环境配置
对于无网络环境，需提前下载：
- 对应版本 Gradle 发行版（放置于 `gradle/wrapper/` 目录）
- 项目依赖的所有 JAR 包（通过 `gradle offline --configuration compileClasspath` 缓存）

**离线运行命令**：./gradlew run --offline


<!-- by 唐文广 -->
## 4. 快速开始
温馨提示：你需要完成环境的配置才能部署本项目，本项目要求JDK最低1.8及以上，安装了Gradle 3.3及以上版本。
按照以下步骤，您可以快速启动本项目：

### 4.1 克隆代码
首先，克隆项目代码到本地：
```bash
git clone https://github.com/anyEkko/logbook-spring-boot-demo.git
```
![alt text](img/image.png)

### 4.2 构建项目
使用 gradle 进行构建：
```bash
gradlew build
```
构建成功结果如下
![alt text](img/gradlewbuild.png)
 
### 4.3 启动服务
运行以下命令启动 Spring Boot 服务：
```bash
gradlew bootRun
```
启动成功后如下：
![alt text](img/gradlewbootRun.png)

### 4.4 访问服务
项目启动后，默认监听 `http://localhost:8080`，您可以通过浏览器或工具（如 Postman）访问测试。  
我们可以访问 `http://localhost:8080/echo/` + 任意你想测试的用例。  
例如：我们访问 `http://localhost:8080/echo/helloworld`。  
我们可以先在网页上看到helloworld字样。  
![alt text](img/helloworld2.png)  
我们在后台也可以清楚看到样例的信息： 
![alt text](img/helloworld.png)
---
- 优点：支持高并发日志处理。


<!--by 伍师杰-->
### 5. 项目架构
本项目采用模块化架构设计，遵循高内聚、低耦合的原则，确保系统的可维护性和可扩展性。架构主要分为以下核心模块：

### 5.1 日志记录模块
实现方式：基于Logbook框架实现HTTP请求/响应的全链路拦截与记录
核心功能：
支持JSON、文本等多种日志格式配置
提供请求/响应内容的精细化过滤规则
支持异步日志写入，避免阻塞主业务流程
可扩展的日志输出渠道（文件、ELK、数据库等）

### 5.2 配置模块
实现方式：基于Spring Boot配置体系，结合Nacos实现动态配置
核心功能：
通过application.yml集中管理应用配置
支持多环境配置隔离（dev/test/prod）
实现配置热更新机制，关键参数修改实时生效
提供配置版本管理和回滚能力

### 5.3 安全模块
实现方式：基于自定义过滤器+注解实现敏感数据处理
核心功能：
自动识别并脱敏身份证号、手机号等敏感信息
支持正则表达式自定义脱敏规则
提供日志审计追踪功能
符合GDPR等数据安全合规要求

### 5.4 控制器模块
实现方式：Spring MVC RESTful风格API设计
核心功能：
清晰的API版本管理（/v1/api/...）
统一的异常处理机制
完整的Swagger接口文档
请求参数自动校验（JSR-303）
模块交互设计
各模块通过定义明确的接口契约进行交互：
采用依赖注入(DI)实现模块解耦
关键交互点设置熔断降级机制
模块间通信统一使用DTO对象
通过Spring Event实现异步事件通知
该架构设计支持横向扩展，后续可通过以下方式增强：
引入模块化加载机制（OSGi）
增加gRPC内部通信协议
支持插件化功能扩展

<!--by 陆发欣-->
## 6.配置说明
### 6.1 代码拓展亮点
可视化软件会根据 YAML 文件的语法特征亮点显示不同的关键字、值等。例如，“logbook”、“format”、“filters”等会被标识为键，并以特定的颜色显示，而“json”、“/api/secure/*”、“true”、“info”等值会以另一种颜色呈现，这可以让我更直观地划分出配置项及其对应的值，便于理解和修改。

### 6.2 智能感知
在编写过程中，Visual 软件将提供智能提示。例如，当我们输入 logbook：“ 并按下 Enter 键时，软件可能会自动提示我们常见的子配置项，如 ”format“、”filters“ 等，帮助我们快速准确地完成代码编写，减少因拼写错误或忘记配置项而导致的领先。到错误。

### 代码显示：
```
format: json            # Log output format: json or text
  filters:
    pattern: /api/secure/*  # Filter rule: match path
    mask: true              # Mask sensitive information for matches
  log-level: info          # Log level
  ```

### 6.3 结构化视图
可视化软件通常会提供结构化的视图面板，我们可以在其中清楚地看到 YAML 文件的整体结构。例如，可以看出 “server” 和 “spring” 是同级别的配置项，而 “port” 是 “server” 的子项，“application” 是 “spring” 的子项，“name” 是 “Application” 的子项，等等。这种结构化的视图可以帮助我们快速定位到具体的配置部分，方便修改和查看。

### 6.4 代码折叠和展开
代码折叠和扩展：对于多级嵌套的 YAML 配置，Visual 软件支持代码折叠和扩展功能。例如，我们可以折叠 “spring” 配置项及其子项，只显示顶级键 “spring”。当我们需要查看或修改里面的 “application” 和 “name” 时，我们可以展开相应的部分。这样可以有效减少视觉干扰，提高处理复杂 YAML 文件时代码的可读性和可维护性。

### 代码显示:
```
port: 8080               # Service listening port
spring:
  application:
    name: logbook-demo     # Application name
```

### 6.5 日志配置
• logbook：日志配置的根节点，包括所有与日志相关的设置。 • format：将日志输出格式设置为 JSON，方便程序分析及与其他系统集成。 • 过滤器：定义过滤器规则，包括路径匹配和敏感信息屏蔽。 • pattern：匹配路径为 /api/secure/*，这意味着将筛选所有以 /api/secure/ 开头的路径。 • mask：设置为 true 以屏蔽匹配路径中的敏感信息。 • log-level：将日志级别设置为 info，并将日志信息记录在 info 级别以上。

### 代码显示：
  ```
format: json            # Log output format: json or text
  filters:
    pattern: /api/secure/*  # Filter rule: match path
    mask: true              # Mask sensitive information for matches
  log-level: info          # Log level
```

### 6.6 服务和应用程序配置
• server：服务监控配置。 • port：设置服务监听端口为 8080，用于接收客户端请求。 • spring：Spring 框架相关配置。 • application：应用程序配置。 • name：设置应用名称为 logbook-demo，用于识别和管理 Spring 生态中的应用。 使用 Visual 软件的优势 在 Visual 软件（如 Visual Studio Code）中编写和管理 YAML 文件时，您可以充分利用以下功能：

代码扩展亮点：不同的配置项和值以不同的颜色显示，便于区分和理解。
智能提示：自动提示常用配置项和值，减少手动输入错误。
结构化视图：提供文件结构概览，方便快速定位具体配置项。
代码折叠：支持折叠和扩展嵌套配置，以提高代码可读性。 通过这些功能，可以高效、准确地完成 YAML 配置文件的编写和维护，确保配置满足业务需求。

### 代码显示：
```
port: 8080               # Service listening port
spring:
  application:
    name: logbook-demo     # Application name
```


<!-- by 谢鹏飞 -->
## 7. 测试方法

本项目附带多种测试方式，以确保功能的正确性和稳定性：

<!-- by 谢鹏飞 -->
### 7.1 JUnit单元测试
- 本项目是一个基于Gradle工程的项目
- 使用JUnit编写的单元测试覆盖核心功能。
- 在build.gradle文件中添加依赖
- JUnit4依赖
- dependencies {
-    testImplementation 'junit:junit:4.13.2'
- }
- 有两种测试测试方式
- 执行以下命令运行测试：
  ```bash
- 1.执行所有测试方法
- gradle test
- 2.执行特定的方法
- 找到该类位于的包和方法
- 示例
- gradle test --tests "com.example.LogbookSpringBootDemoApplicationTest.testAdd"
  ```
<!-- by 谢鹏飞 -->
### 7.2 接口测试
<!-- by 谢鹏飞 -->
### 7.2.1 使用Postman方法测试
- 通过Postman工具进行接口测试,Postman是一个功能强大的API测试工具,支持发送各种类型的HTTP请求并查看响应。
- 打开Postman应用
- 创建一个GET请求,或者其他请求如(GET、POST、PUT、DELETE等) 
- 示例请求：
- 执行项目中一个GET请求
- 在请求URL中输入http://localhost:8080/echo/{message}
- 将{message}替换成想要的消息
- 点击 Send 按钮发送请求
- Send成功后即可查看响应回来的数据
- 验证响应数据是否符合预期


<!-- by 谢鹏飞 -->
### 7.2.2 Swagger文档测试

- 在 build.gradle 文件中添加依赖
- dependencies {
-    implementation 'org.springdoc:springdoc-openapi-ui:1.6.11'
- }
- 启动项目,Swagger文档会自动生成。
- 通过浏览器访问url:localhost:8080/swagger-ui.html SwaggerUI页面进行查看
- 选择需要测试的接口,填写参数并点击Try it out按钮发送请求。
- 示例请求:
- 在请求URL中输入http://localhost:8080/echo/{message}
- 将{message}替换成想要的消息
- 发送请求后,即可查看响应回来的信息
- 验证响应数据是否符合预期
- Swagger文档测试的优点:
- 相比于Postman测试工具,它可直接在浏览器进行接口测试

