# Project Overview
This project is a fully functional **e-commerce platform** demonstrating the implementation of **modern software development principles**, including:
- **MVC architecture** for organized code structure  
- **Robust database schema** for efficient data management  
- **Modular services** to ensure scalability and maintainability  
- **Third-party payment gateway integration** with **Razorpay** for seamless transactions  

## Key Features
- **User Authentication:** Secure login and registration system  
- **Product Catalog Management:** Add, update, and manage product listings  
- **Shopping Cart:** Add-to-cart, modify, and remove items with ease  
- **Order Management:** Streamlined order creation, tracking, and processing  
- **Payment Processing:** Secure and reliable payments via **Razorpay**

## Features

1. **Product Management:**
    - Product catalog with categories and inventory management
    - Integration of images for products
	
2. **User Management:**
    - User registration and login
    - Role-based access control

3. **Shopping Cart:**
    - Add, update, and remove items from the cart
    - Display cart total and individual item prices

4. **Order Management:**
    - Order placement and summary
    - Integration with payment gateway (RazorPay) for secure transactions

5. **Payment Processing:**
    - RazorPay payment link generation
    - Handling payment success and failure scenarios

6. **Database Design:**
    - Relational database schema optimized with foreign keys and indexing
    - Scalable and normalized schema for efficient data retrieval

7. **Error Handling:**
    - Custom exceptions for meaningful error messages
    - Graceful handling of runtime errors

## Technologies Used
1. **Backend:**
    - Java
    - Spring Boot 

2. **Database:**
    - MySQL

3. **Payment Gateway:**
    - RazorPay for secure and seamless payment processing

4. **Tools and Libraries:**
    - Hibernate for ORM


## Getting Started

### Prerequisites
- Java 17
- Maven Installed (3.9.9) 
- MySQL 8.2 Installed
- RazorPay account and API keys

### Initial Steps
1. Setup database:
	```
	create database productservice;
	create database userservice;
	create database paymentservice;
	create user 'shubham'@'localhost';
	grant all privileges on productservice.* to 'shubham'@'localhost';
	grant all privileges on userservice.* to 'shubham'@'localhost';
	grant all privileges on paymentservice.* to 'shubham'@'localhost';

	```
2. Clone the repositories:
    ```sh
    git clone https://github.com/ShubhamMore/scaler-product-service.git
    ```
	```sh
    git clone https://github.com/ShubhamMore/scaler-user-service.git
    ```
	```sh
    git clone https://github.com/ShubhamMore/scaler-payment-service.git
    ```
	
3. Update Configurations
	- In payment service `application.properties` update `razorpay.key_id=<Your razorpay key id>` and `razorpay.key_secret=<Your razorpay key secret>`
	- Update database credentials if started at different port on your machine.

### Start Applications:

1. Navigate to the project directores and run:
	## For Product Service
    ```sh
    mvn clean package
	java -jar .\target\project.product-0.0.1-SNAPSHOT.jar
    ```
	
	## For User Service
    ```sh
    mvn clean package
	 java -jar .\target\project.user-0.0.1-SNAPSHOT.jar
    ```
	
	## For Payment Service
    ```sh
    mvn clean package
	java -jar .\target\project.payment-0.0.1-SNAPSHOT.jar
    ```

### Accessing Apis
-	Postman collection is avilable in this project to access all apis on postman with sample data.
-	Swagger is also integrated in all services which can be accessed as:-
	-	Product service apis at `http://localhost:8080/swagger-ui/index.html`.
	-	User  service apis at `http://localhost:9001/swagger-ui/index.html`.
	-	Payment service apis at `http://localhost:4001/swagger-ui/index.html`.


### Accessing Apis
-	Create user with user service
-	Product service needs oauth2 authentication from userservice to access its apis (oauth2 configuration is already present in postman collection).

### OAuth2 Credentials
-	Client Id :- scaler
-	Client Secret :- scaler-secret
-	Above config can be changed at application.properties of user service.

## License
This project is licensed under the MIT License.