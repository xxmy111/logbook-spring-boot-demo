<!-- by 尤淇 -->
## 术语词汇
项目相关
​​API​​：应用程序接口，用于不同软件组件间的交互。
​​Logbook​​：用于记录HTTP请求和响应的日志工具。
系统架构相关
​​Software system architecture​​：软件系统的整体结构。
​​Microservices architecture​​：将应用分解为一组小型服务的架构。
性能与问题排查相关
​​Observability​​：系统可被观察和理解的能力。
​​Debugging capabilities​​：开发者定位和修复错误的能力。
​​Performance bottlenecks​​：限制性能提升的系统环节。
​​Anomalies​​：系统中的异常行为。
数据处理相关
​​JSON​​：轻量级数据交换格式。
​​XML​​：可扩展标记语言。
​​Plain text​​：纯文本格式。
网络通信相关
​​HTTP​​：超文本传输协议。
​​Request/Response​​：客户端与服务器间的请求和响应。
​​Request URL/Method/Parameters/Headers​​：请求的URL、方法、参数和头部信息。
​​Response status code/Time​​：响应的状态码和处理时间。
安全与合规相关
​​Sensitive information​​：敏感数据，如密码、Token。
​​Data compliance​​：数据合规性要求。
分布式系统相关
​​Distributed systems​​：由多个独立节点组成的系统。
日志处理相关
​​API call logs​​：API调用日志。
​​Log formatting/filtering/recording/monitoring​​：日志的格式化、过滤、记录和监控。

<!-- by 朱淼佳 -->




=======
# 技术术语表 (Glossary)

## 核心概念
| 中文术语         | 英文术语                     | 定义说明                                                                 |
|------------------|-----------------------------|--------------------------------------------------------------------------|
| 拦截器           | Interceptor                 | 在请求处理前后进行拦截和处理的组件，用于实现横切关注点如日志记录、权限校验等    |
| 解耦             | Decoupling                  | 将系统各模块分离设计，降低组件间的依赖性，提高灵活性和可维护性                   |
| 日志适配器       | Log Adapter                 | 转换日志数据格式的中间件组件，支持JSON/XML等不同格式的输出                        |

## 配置管理
| 中文术语         | 英文术语                     | 定义说明                                                                 |
|------------------|-----------------------------|--------------------------------------------------------------------------|
| 配置文件         | Configuration File          | 定义系统运行参数的文件(如logback.xml)，支持YAML/JSON等格式配置日志行为           |
| 动态配置         | Dynamic Configuration       | 支持运行时调整系统参数(如日志级别)而无需重启应用的能力                            |

## 性能优化
| 中文术语         | 英文术语                     | 定义说明                                                                 |
|------------------|-----------------------------|--------------------------------------------------------------------------|
| 异步日志处理     | Asynchronous Logging        | 采用非阻塞方式记录日志，通过独立线程处理避免影响主业务流程性能                      |
| 批量写入         | Batch Writing              | 将多条日志合并后一次性写入存储，减少I/O操作次数提升效率                           |

## 安全控制
| 中文术语         | 英文术语                     | 定义说明                                                                 |
|------------------|-----------------------------|--------------------------------------------------------------------------|
| 敏感信息屏蔽     | Sensitive Data Masking      | 自动识别并脱敏处理密码/Token等敏感字段的日志记录技术                            |
| 白名单机制       | Whitelist                  | 仅允许符合预定义规则的请求通过或记录的安全策略                                 |
| 黑名单机制       | Blacklist                  | 阻止或忽略特定请求的访问控制策略                                            |

## 扩展集成
| 中文术语         | 英文术语                     | 定义说明                                                                 |
|------------------|-----------------------------|--------------------------------------------------------------------------|
| 扩展接口         | Extension Interface         | 提供给开发者实现自定义功能的编程接口(如Hook/Plugin机制)                       |

| 监控分析平台     | Monitoring Platform         | 用于日志分析和性能监控的第三方系统(如ELK/Prometheus/Grafana等)                |


<!-- by 莫永启 -->
# 专业术语词汇
|  中文术语                  | 英文术语                         | 说明                                                              |
|---------------------------|---------------------------------|--------------------------------------------------------------------------|
| 操作系统                  | Operating System (OS)            | Windows、macOS、Linux 等系统软件，管理硬件与软件资源。                 |
| JDK                       | Java Development Kit             | Java 开发工具包，含编译器、运行时环境（需 JDK 11+）。                   |
| Gradle                    | Gradle                          | 自动化构建工具，支持依赖管理和多项目构建（需 3.3+ 版本）。               |
| 网络环境                  | Network Environment             | 互联网连接条件，需稳定网络用于下载依赖（国内用户可能需要 VPN）。         |
| 梯子                      | VPN (Virtual Private Network)    | 网络代理工具，用于访问国际服务（如 GitHub）。                            |
| gradlew                   | Gradle Wrapper                  | Gradle 的包装脚本，用于隔离构建环境（`gradlew run` 命令）。             |
| 依赖                      | Dependencies                    | 项目所依赖的外部库或模块，通过 Gradle 自动下载。                         |
| 稳定的互联网连接           | Stable Internet Connection       | 网络需具备持续连通性，避免构建或运行时中断。                             |

---
### 关键说明：
1. **版本要求**：JDK 和 Gradle 的版本号（如 JDK 11+、Gradle 3.3+）属于具体配置，未列入术语表。
2. **工具命令**：`gradlew run` 是操作命令，术语表中仅保留核心工具名（Gradle Wrapper）。
3. **网络工具**：“梯子”为中文俚语，对应英文技术术语为 **VPN**，括号内补充全称。


<!-- by 唐文广 -->
# 术语词汇表 (Glossary of Terms)

| 中文术语 (Chinese Term) | 英文术语 (English Term) |
|--------------------------|--------------------------|
| 克隆                     | Clone                   |
| Gradle                  | Gradle                   |
| 构建                     | Build                   |
| Spring Boot             | Spring Boot Framework    |
| Postman                 | Postman                  |
=======
| 监控分析平台     | Monitoring Platform         | 用于日志分析和性能监控的第三方系统(如ELK/Prometheus/Grafana等)                |

<!--by 伍师杰-->
### 术语
Modular architecture    模块化架构
HTTP requests/responses   HTTP请求/响应
Logbook framework   Logbook框架
Request parameter validation   请求参数验证
 Regular expressions       正则表达式
Hot configuration update   热配置更新
Interface contracts    接口协议
API version management   API版本管理
Circuit breaker   断路器
Maintainability   可维护性



<!--by 陆发欣-->
## 配置说明术语
| 英文术语        | 中文术语   | 定义说明                               |
| :---------- |   :----- |     :--------------------------------- |
| logbook     | 日志簿    | 日志记录相关的组件或模块名称，用于配置日志功能            |
| format      | 格式     | 日志输出的格式，决定日志内容是 json 格式还是 text 格式  |
| filters     | 过滤器    | 定义日志的过滤规则，用于对特定请求进行特殊处理            |
| pattern     | 模式     | 过滤规则中的匹配路径模式，用于确定哪些请求需要应用过滤规则      |
| mask        | 遮蔽     | 布尔值属性，指示是否对匹配请求结果进行敏感信息屏蔽          |
| log-level   | 日志级别   | 日志记录的级别，决定哪些级别的日志信息会被记录下来          |
| server      | 服务器    | 定义服务器相关设置，如监听端口等                   |
| port        | 端口     | 服务监听的端口号，用于接收客户端请求                 |
| spring      | 框架     | 开源的 Java 框架，用于定义与 Spring 应用程序相关的配置 |
| application | 应用程序   | 应用程序或应用相关的配置，如应用名称等                |


<!--by谢鹏飞-->
1.中文术语:开发环境-->英文术语:Development environment
2.中文术语:测试用例-->英文术语Test cases
3.中文术语:依赖关系-->英文术语:Dependencies
4.中文术语:执行测试-->英文术语:execute tests
5.中文术语:测试方法-->英文术语:Test method
6.中文术语:包和方法-->英文术语:Package and method
7.中文术语:有效载荷-->英文术语:Payload
8.中文术语:传递请求-->英文术语:Transmit the request
9.中文术语:传输-->英文术语:Transmission
10.中文术语:响应数据-->英文术语:Response data


