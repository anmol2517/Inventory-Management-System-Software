### Inventory Management System - 
---

# **Inventory Management System (IMS)**  
A web-based application designed for businesses to track and manage inventory efficiently. This project leverages **Spring Boot**, **Thymeleaf**, **MongoDB**, and the **Spring MVC pattern** to provide an intuitive interface and backend functionality.  

---

## **Table of Contents**  
- [Introduction](#introduction)  
- [Features](#features)  
- [Technologies Used](#technologies-used)  
- [Prerequisites](#prerequisites)  
- [Setup Instructions](#setup-instructions)  
- [Project Folder Structure](#project-folder-structure)  
- [Project Workflow](#project-workflow)  
- [Endpoints](#endpoints)  
- [License](#license)  

---

## **Introduction**  
The Inventory Management System is a simple yet powerful tool for managing products in an inventory. Users can:  
- Add new products.  
- Search existing products.  
- Delete products from the inventory.  
- Generate basic analysis reports for inventory insights.  

---

## **Features**  
1. **Add Products**: Dynamically generates unique product IDs and stores product details.  
2. **Search Products**: Retrieve product details using the product ID.  
3. **Delete Products**: Remove products from the database using the product ID.  
4. **Product Reports**: Analyze maximum and minimum product availability with visual charts using Chart.js.  

### **Product Attributes**:  
- Product ID (dynamically generated)  
- Product Category  
- Product Name  
- Product Rating  
- Quality  
- Maximum Number of Products  
- Minimum Number of Products  
- Username (added by)  
- User Email Address  
- User Phone Number  

---

## **Technologies Used**  
- **Backend**: Spring Boot, Spring MVC, MongoDB  
- **Frontend**: Thymeleaf, Bootstrap, Chart.js  
- **Database**: MongoDB  
- **Build Tool**: Gradle  

---

## **Prerequisites**  
Ensure the following tools and dependencies are installed on your system:  
- JDK (Java Development Kit) 17+  
- MongoDB (with default port 27017)  
- Spring Tool Suite (STS) or IntelliJ IDEA  
- Gradle Build System  

---

## **Setup Instructions**  
1. **Clone the repository**:  
   ```bash  
   git clone https://github.com/your-username/inventory-management-system.git  
   cd inventory-management-system  
   ```  

2. **Setup MongoDB**:  
   - Ensure MongoDB is running locally on `localhost:27017`.  
   - Database name: `IMS`.  

3. **Configure application.properties**:  
   Update `src/main/resources/application.properties`:  
   ```properties  
   spring.data.mongodb.host=localhost  
   spring.data.mongodb.port=27017  
   spring.data.mongodb.database=IMS  
   ```  

4. **Build and run the project**:  
   ```bash  
   ./gradlew bootRun  
   ```  

5. **Access the application**:  
   Open your browser and navigate to `http://localhost:8080`.  

---

## **Project Folder Structure**  
```
src  
├── main  
│   ├── java  
│   │   └── com.example.ims  
│   │       ├── controller      // Controller Layer  
│   │       ├── model           // POJO (Product.class)  
│   │       ├── repository      // MongoRepository  
│   │       └── service         // Optional Business Logic Layer  
│   └── resources  
│       ├── templates           // Thymeleaf HTML files  
│       └── application.properties  
├── build.gradle                // Project Dependencies  
```

![image](https://github.com/user-attachments/assets/095d65cd-d020-4d78-8622-3fcbf6b0edb4)

---

## **Project Workflow**  

### **Model Layer**  
`Product.class` contains attributes such as `Product ID`, `Name`, and `Category`. Lombok annotations manage setters, getters, and constructors.  

### **Controller Layer**  
Handles incoming API requests:  
- `@GetMapping("/")` – Display the homepage.  
- `@PostMapping("/newProduct")` – Add a new product.  
- `@PostMapping("/searchProduct")` – Search for a product by ID.  
- `@PostMapping("/deleteProduct")` – Delete a product by ID.  
- `@GetMapping("/productAnalysis")` – Display product analysis charts.  

### **Repository Layer**  
`ProductRepo` extends `MongoRepository` to handle CRUD operations.  

### **View Layer**  
HTML templates (Thymeleaf) integrate backend logic and display dynamic content.  

---

## **Endpoints**  

| Endpoint                 | HTTP Method | Description                        |  
|--------------------------|-------------|------------------------------------|  
| `/`                      | GET         | Display the index page.           |  
| `/newProduct`            | POST        | Add a new product.                |  
| `/searchProduct`         | POST        | Search for a product by ID.       |  
| `/deleteProduct`         | POST        | Delete a product by ID.           |  
| `/productAnalysis`       | GET         | Show product analysis charts.     |  

---

## **License**  
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.  

--- 

Feel free to customize it further as per your project needs! Let me know if you need more details. 😊  
