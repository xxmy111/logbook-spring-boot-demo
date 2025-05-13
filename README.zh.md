<!-- by 朱淼佳 -->

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
=======
- 优点：支持高并发日志处理。

