The SIM Activation Microservice is a Spring Boot application that facilitates SIM card activation by accepting incoming POST requests containing the SIM ICCID and the customer's email address. 
These requests are forwarded to an external actuator service, which processes the activation and returns a response indicating whether the activation was successful. 
This microservice is designed to be simple to use and easy to configure locally. 
To run the application, you need Java 11 or later and Maven (or the Maven Wrapper provided in the project). First, start the actuator service by executing the SimCardActuator.jar file located in the services folder using the command java -jar services/SimCardActuator.jar. 
The actuator runs on http://localhost:8444. Next, start the Spring Boot application using ./mvnw spring-boot:run, which will make the microservice accessible on http://localhost:8080. The primary endpoint of this application is /sim/activate, which accepts POST requests with a JSON body containing the ICCID and customer email. 
For example, a request body might look like {"iccid": "12345678901234567890", "customerEmail": "user@example.com"}, and the service will respond with either "SIM activation successful!" or "SIM activation failed." based on the response from the actuator. 
You can test this functionality using tools like Postman or curl. The project uses Java 11, Spring Boot, Maven, and RestTemplate for handling HTTP communication. 
The code is modular, with well-structured components for handling requests, forwarding them to the actuator, and processing responses. 
Future enhancements to this service could include integrating a database for persistence, adding robust exception handling, and implementing comprehensive unit and integration tests. 
This project demonstrates the principles of microservice development, showcasing how to handle incoming requests, communicate with external services, and respond with meaningful results.
