
<!--by XiePengFei-->
7. Testing Methods
- This project includes various testing methods to ensure the correctness and stability of its functions:
7.1 JUnit Unit Testing
- This project is a Gradle-based project.
- Unit tests covering core functionalities are written using JUnit.
- Dependencies are added in the build.gradle file.
- JUnit 4 dependency:
- dependencies {
- testImplementation 'junit:junit:4.13.2'
- }
- There are two ways to run tests:
- Run the following command to execute all test methods:
- bash
- gradle test
- Run a specific test method:
- Locate the package and method of the class.
- Example:
- gradle test --tests "com.example.LogbookSpringBootDemoApplicationTest.testAdd"

7.2 Interface Testing
7.2.1 Testing with Postman
- Postman is a powerful API testing tool that supports sending various types of HTTP requests and viewing responses.
- Open the Postman application.
- Create a GET request or other types of requests (e.g., GET, POST, PUT, DELETE).
- Example request:
- Execute a GET request in the project.
- Enter the URL: http://localhost:8080/echo/{message}
- Replace {message} with the desired message.
- Click the Send button to send the request.
- After a successful Send, you can view the response data.
- Verify whether the response data meets the expectations.

7.2.2 Testing with Swagger Documentation
- Add dependencies in the build.gradle file:
- dependencies {
- implementation 'org.springdoc:springdoc-openapi-ui:1.6.11'
- }
- After starting the project, the Swagger documentation will be automatically generated.
- Access the Swagger UI page via the browser at the URL: http://localhost:8080/swagger-ui.html
- Select the interface to be tested, fill in the parameters, and click the Try it out button to send the request.
- Example request:
- Enter the URL: http://localhost:8080/echo/{message}
- Replace {message} with the desired message.
- After sending the request, you can view the response information.
- Verify whether the response data meets the expectations.
- Advantages of Swagger documentation testing:
- Compared to Postman, it allows direct interface testing in the browser.

