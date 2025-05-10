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