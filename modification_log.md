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