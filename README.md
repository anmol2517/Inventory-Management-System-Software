# Inventory-Management-System-Software

Inventory Management System plays an important role in Business for tracking the Inventory, and It is used for tracking and movement of goods. In this article, we have provided some basic functionality for the Inventory Management System like an Analysis report of goods, adding new Products to the System, Searching the existing product details, and other one is deleting an existing product from the System. In this article, we have mentioned an Inventory Management System as an IMS App, for this tool we have used Spring Boot with an MVC pattern with Thymeleaf for front-end integration.

This Application handles the product details and performs different operations on every record in the Inventory Management System Application.

## Prerequisites
>> Spring Boot
>> Thymeleaf
>> MongoDB
>> Spring MVC Pattern
>> Bootstrap Framework 
>> Project Type is Gradle 
>> Spring Tool Suite IDE (STS)

This Spring Boot Inventory Management System Web Application with MVC Pattern and the Thymeleaf is used for providing Dynamic HTML content in this tool, The MongoDB is used for data storage purposes, and the other one is Bootstrap framework used for creating responsive web applications.

## Product Details
For a Product, we have different attributes like:

1. Product ID
2. Product Category
3. Product Name
4. Product Rating
5. Quality
6. Maximum number of Products
7. Minimum number of Products
8. Username (Product Added by)
9. User Email Address
10. User Phone Number

In this Inventory Management System Project, the Product ID is dynamically Generated which have a String and Number format. After Generating the Product ID then Inserted Other product details with ID in the Database.

## Project Creation Steps
1. Create a Spring Stater Project using Spring Tool Suite IDE ( reference )
2. After successfully creation of Project, then create a Package for different layers in this web Application namely packages for Controller, POJO, Repository, and other packages if you want.
3. In the Controller Package create one ProductController class after that create one Project POJO class in the POJO package, After Creating one Product Repository interface in the Repository package. After that create one 4. 4. HTML file in the Templates which is placed in the project resource folder.
5. Now Implement Controller layer code after that develop pojo class code, and after that develop repository class code.
6. After completion of Back-end functionalities then develop the front-end page for visibility.
7. After successfully completion of Front-End and Back-End then Integrate both of them by using the Thymeleaf Framework.
8. After that Run this Application as Spring Boot App.

>> Required Project Dependencies : These Project Dependencies are available in Spring Stater Project While creating the Project. After the Creation of this Project, You can see These Dependencies in the build.gradle file in the Project.

- Project Folder Structure

![image](https://github.com/user-attachments/assets/095d65cd-d020-4d78-8622-3fcbf6b0edb4)

## Code Development Process
Now we will see the development Process of Inventory Management System using Spring Boot, and Spring MVC. In the development process first, we create one POJO class for Products. In this POJO class, we keep Attributes of Product like Product ID, Like *Product Category, Product Name, Product Rating, Quality, Maximum number of Products, Minimum number of Products, Username (Product Added by), User Email Address, User Phone Number.* This POJO class also has Setters and Getters methods for data handling with Parameterized and non-parameterized constructors in the Product POJO class.

## Database Connection
In Inventory Management System Application, We perform different Operations on data. That's why we need a data storage for storing the data. For this, I Selected MongoDB Database for data Storage. In Database Connection, We need three attribute values Host name, Port number of MongoDB, And the other one is Database Name. The Database Connection Attributes are kept in the application properties file. We have already provided the folder structure. In that application properties file is available.

>> Here ims is the Database name, 27017 is the port number of MongoDB, And we have used Localhost for running the system on my local system.

## Model Layer
For this, we have created one POJO class in pojo package which is Product.class, this POJO class contains all the attributes of the Product and It has Setters and Getters and also two different constructors Parameterized and non-parameterized constructors. I used one dependency, Lombok which is available in Spring Boot. This Annotation is used for Parameterized and non-parameterized constructors by using *@Data, @AllArgsConstructor, @NoArgsConstructor, @Document.*

- Product Class
- View Layer
- Repository
- Controller Layer
- Display HTML Page
- Search Product Details
- Delete Product
- Product Report

The Inventory Management System is used in Business tracking and counting, and it provides an in-detail report about the Available Inventory. Here we have created a basic Inventory Management *System using Spring Boot with Spring MVC Pattern*. Your Basic knowledge about annotations, the working process of *Spring MVC pattern*, and others for a Better Understanding of this Article.
