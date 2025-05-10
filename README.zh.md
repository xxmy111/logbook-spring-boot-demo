
<!-- by 唐文广 -->
## 4. 快速开始

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
