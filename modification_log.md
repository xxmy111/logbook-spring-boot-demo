

=======
<!-- by 唐文广 -->
# AI修改记录对照

## 1. 克隆代码部分
- **新增一条命令**：`cd logbook-spring-boot-demo`，用户补充了进入克隆目录的操作。

## 2. 构建项目部分
- **构建工具更改**：从 **Gradle** 改为 **Maven** 实际我们使用的构建工具应为 **Gradle** 。
- **命令更改**：
  - AI使用了 `mvn clean install`。
  - 用户更改为 `gradlew build`。
  
## 3. 启动服务部分
- **启动命令更改**：从 Gradle 的 `gradlew bootRun` 改为 Maven 的 `mvn spring-boot:run` 实际我们使用的启动命令应为 `gradlew bootRun` 。

## 4. 环境配置提示
- **删除内容**：AI未对关于环境配置（JDK 和 Gradle 版本要求）的提示。

## 5. 访问服务部分
- **简化内容**：
  - AI删除了具体的访问路径示例（如 `/echo/helloworld`）。
  - AI省略了网页和后台显示的截图描述。


<!--by伍师杰-->
### 
1.询问了AI此项目运用了什么项目框架，分别是什么模块，它们的作用是什么？
2.问了AI这些模块的运行方式
3.询问AI这段文字还有什么可以完善的？
4.让AI将这段文字进行了翻译


<!-- by 谢鹏飞 -->
7.1 JUnit单元测试
修改内容：将JUnit3依赖升级为JUnit4依赖。
修改原因：JUnit4提供了更强大的功能和更好的扩展性，能够更好地满足项目测试需求。

运行测试命令修改：
原命令：gradle test（无变化）
新增命令：gradle --tests "*Test"，用于运行所有以“Test”结尾的测试类。

7.2 接口测试
7.2.1 使用Postman方法测试
修改内容：增加了对Postman环境变量的支持。
修改原因：通过环境变量可以更灵活地切换测试环境（如开发环境、测试环境、生产环境）。
修改后的操作：
在Postman中创建环境变量，例如BASE_URL，值为http://localhost:8080。
修改请求URL为{{BASE_URL}}/echo/{message}，使用环境变量替换硬编码的URL。

7.2.2 Swagger文档测试
修改内容：将Swagger依赖升级为最新的版本，并增加了对OAuth2认证的支持。
修改原因：新版本的Swagger提供了更好的性能和更多的功能，同时支持OAuth2认证能够更好地满足安全接口的测试需求。
修改后的代码：
gradle
复制
dependencies {
    implementation 'org.springdoc:springdoc-openapi-ui:1.7.0'
}
新增内容：
在Swagger UI页面中，增加了OAuth2认证的配置选项，用户可以通过输入认证信息后进行接口测试。
示例：在测试需要认证的接口时，用户需要先在Swagger页面的“Authorize”按钮中输入OAuth2认证信息（如Token），然后才能发送请求。
