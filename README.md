<h2>Overview</h2>
A simple Spring Boot REST application that uses Spring Data REST mechanism and allows you to perform all CRUD operations on a list of employees. Employees are in the database and information is transferred using JSON
<br>
<br>
The application allows you to get a list of all employees, a single employee by ID, add a new employee, modify an existing employee and delete an employee
<br>
<br>
When creating the REST API, we adhered to generally accepted standards:
<br>
<br>

| HTTP method  | URL | CRUD operation |
| ------------- | ------------- | ----------- |
| GET  | api/employees  | getting all employees |
| GET  | api/employees/{employeeId}  | getting single employee |
| POST  | api/employees  | adding an employee |
| PUT  | api/employees/{employeeId}  | employee updating |
| DELETE  | api/employees/{employeeId}  | employee removal |

Settings for connection to the database are specified in the file application.properties (/src/main/resources/application.properties)
<br><br>
All CRUD operations are performed using interface "EmployeeRepository" that extends interface "JpaRepository"
<br><br>
To run the application on the server we use the class "SpringBootRestApplication" which is created simultaneously with the project creation and gets the name automatically depending on the project name
<h3>Configuration</h3>
The application is configured with Spring Initializr (start.spring.io) using starter packages "Spring Web", "Spring Data JPA" and "MySQL Driver"<br>
To use Spring Data REST mechanism we added dependency "spring-boot-starter-data-rest"<br>
Server support is built in
<h3>Testing</h3>
In order to test all CRUD operations using all HTTP methods we resorted to the "Postman" application
<h3>Application tracking</h3>
In order to track the application's performance, we use Spring Actuator<br>
To do this we added dependency "spring-boot-starter-actuator"<br>
We can see information about the application status, information about the application itself, information about all beans registered in the Spring Container, information about all Mappings<br><br>
All settings concerning this data are specified in the file "application.properties" (/src/main/resources/application.properties)
<br><br>
In order to allow only certain users to see this information we have implemented an authentication procedure using Spring Security. Username and password are specified in the file "application.properties" (/src/main/resources/application.properties)
