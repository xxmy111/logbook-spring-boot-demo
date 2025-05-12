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

