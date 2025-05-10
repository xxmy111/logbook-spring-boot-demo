
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
