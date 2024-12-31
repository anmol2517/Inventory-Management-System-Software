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
1. Create a Spring Stater Project using Spring Tool Suite IDE ( reference ).
2. After successfully creation of Project, then create a Package for different layers in this web Application namely packages for Controller, POJO, Repository, and other packages if you want.
3. In the Controller Package create one ProductController class after that create one Project POJO class in the POJO package, After Creating one Product Repository interface in the Repository package. After that create one.
4. HTML file in the Templates which is placed in the project resource folder.
5. Now Implement Controller layer code after that develop pojo class code, and after that develop repository class code.
6. After completion of Back-end functionalities then develop the front-end page for visibility.
7. After successfully completion of Front-End and Back-End then Integrate both of them by using the Thymeleaf Framework.
8. After that Run this Application as Spring Boot App.


>> Required Project Dependencies: These Project Dependencies are available in Spring Stater Project While creating the Project. After the Creation of this Project, You can see These Dependencies in the build.gradle file in the Project.

```
dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-data-mongodb'
    implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
    implementation 'org.springframework.boot:spring-boot-starter-web'
    compileOnly 'org.projectlombok:lombok'
    developmentOnly 'org.springframework.boot:spring-boot-devtools'
    annotationProcessor 'org.projectlombok:lombok'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```

## Project Folder Structure

![image](https://github.com/user-attachments/assets/095d65cd-d020-4d78-8622-3fcbf6b0edb4)

## Code Development Process
Now we will see the development Process of Inventory Management System using Spring Boot, and Spring MVC. In the development process first, we create one POJO class for Products. In this POJO class, we keep Attributes of Product like Product ID, Like *Product Category, Product Name, Product Rating, Quality, Maximum number of Products, Minimum number of Products, Username (Product Added by), User Email Address, User Phone Number.* This POJO class also has Setters and Getters methods for data handling with Parameterized and non-parameterized constructors in the Product POJO class.

## Database Connection
In Inventory Management System Application, We perform different Operations on data. That's why we need a data storage for storing the data. For this, I Selected MongoDB Database for data Storage. In Database Connection, We need three attribute values Host name, Port number of MongoDB, And the other one is Database Name. The Database Connection Attributes are kept in the application properties file. We have already provided the folder structure. In that application properties file is available.

>> Here IMS is the Database name, 27017 is the port number of MongoDB, And we have used Localhost for running the system on my local system.

## Model Layer
For this, we have created one POJO class in pojo package which is Product.class, this POJO class contains all the attributes of the Product and It has Setters and Getters and also two different constructors Parameterized and non-parameterized constructors. I used one dependency, Lombok which is available in Spring Boot. This Annotation is used for Parameterized and non-parameterized constructors by using *@Data, @AllArgsConstructor, @NoArgsConstructor, @Document.*

- Product Class
>> *@Data Annotation* is used for managing Setters and Getters methods in the Product POJO class, The *@Document* is used for creating Collection name in the Database, *@AllArgsConstructor* is used for managing parameterized constructor and *@NoArgsConstructor* is used for managing the default constructor.

- View Layer
>> One HTML page in the Templates folder in the Project Folder Structure. And we have used Thymeleaf for Providing Dynamic Content of The HTML page in the Inventory Management System Project.

>> Thymeleaf URL in HTML element. *used th: action, th:object, th:if*, and others for performing different operations on the HTML page. The Back-End logic is also handled by Thymeleaf, the result is visible on the HTML page.

- Repository
>> Already mentioned in the above *creation repository package*. In this Web Application, we have created one Mongo Repository by *@Repository Annotation* for Handling crud operations in this application, this is interact with Database. **This Interface extends to MongoRepository.**

>> Provide *Product.class* ( POJO Class ) and *product ID* data type as Arguments to the *MongoRepository.* In Product pojo the ID type is String that's why we have passed String as an argument. This *ProducRepo* interface is used for performing CRUD operations on the data.

- Controller Layer
>>  The Controller class is created by using @Controller Annotation. This class handles the incoming API requests, based on the request type it can provide like post, get, delete like that. It can trigger the business logic and provide the output on the web page by using the Thymeleaf Framework.

Code performs different operations like displaying the HTML index page, adding product details as well as displaying the analysis report of the Product.

```
  <properties>
  <comment>Credentials for the database.</comment>
    <entry key="username">root</entry>
    <entry key="password">root</entry>
  </properties>
```
- *@GetMapping("/productAnalysis")*
- *@GetMapping("/")*
- *@PostMapping("/newProduct")*
- *@PostMapping("/searchProduct")*
- *@PostMapping("/deleteProduct")*

- Display HTML Page
>> *index.html* page I used Thymeleaf for integrating back-end logic with front-end view. By using *GET API* request.

- Insert New Product Details
>> New product data with the help of the *ProductRepo* interface. This Repository provides one method which is the same method. This method is used to save data in the database.

>> Created one *POST* mapping for saving product data, or this API one HTML Form is opened and it will ask some detail about the product once submitted that data. By using the Random method, we have generated one Unique number for that number as PD as a prefix, and after that con-cat both of them then we get the Unique Product ID.

- Search Product Details
>> A product detail by using product ID. If Product details exist, It displays the product details otherwise The Thymeleaf shows one Alert message if no data exists.

>> If want to search for any product details, we need the product ID then only we search product details. For this we have created one POST API, that is searchProduct. When we hit this API, it will open one form and ask for product ID then Click on the Search Button. If the product ID does not exist, it will show one alert message to you.

- Delete Product
>> Its ID, for this we have created one POST method API. When you hit API, it will ask you for the product ID. If you provide a valid ID, then the product is removed from the database otherwise it will show one error message like an alert message.

- Product Report
>> One basic product report on a maximum and minimum number of product items with their category. For charts creation, we have used chart js cdn

The Inventory Management System is used in Business tracking and counting, and it provides an in-detail report about the Available Inventory. Here we have created a basic Inventory Management *System using Spring Boot with Spring MVC Pattern*. Your Basic knowledge about annotations, the working process of *Spring MVC pattern*, and others for a Better Understanding of this Article.
