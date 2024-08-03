# Veltech-bank Here is a README file for your Veltech-bank application:

---

# Veltech-bank Application

## Introduction

Veltech-bank is a simple banking application developed using Java, JSP, Servlets, and JDBC with MySQL. This application allows users to register, login, view their account details, deposit funds, withdraw funds, view transaction history, and close their accounts.

## Features

- User Registration
- User Authentication
- View Account Details
- Deposit Funds
- Withdraw Funds
- View Transaction History
- Close Account

## Technologies Used

- Java
- JSP (JavaServer Pages)
- Servlets
- JDBC (Java Database Connectivity)
- MySQL
- HTML/CSS

## Prerequisites

- JDK (Java Development Kit) 8 or higher
- Apache Tomcat 8 or higher
- MySQL 5.7 or higher
- MySQL Workbench (optional, for database management)

## Database Setup

1. Create a MySQL database named `veltech_bank`.

2. Create a `customer` table with the following schema:

   ```sql
   CREATE TABLE customer (
       accountNo VARCHAR(20) PRIMARY KEY,
       fullName VARCHAR(100),
       address VARCHAR(200),
       mobileNo VARCHAR(15),
       emailId VARCHAR(100),
       accountType VARCHAR(20),
       initialBalance DOUBLE,
       dateOfBirth DATE,
       idProof VARCHAR(100),
       tempPassword VARCHAR(100),
       photoFileName VARCHAR(100)
   );
   ```

3. Create a `transactions` table with the following schema:

   ```sql
   CREATE TABLE transactions (
       transactionId INT AUTO_INCREMENT PRIMARY KEY,
       accountNo VARCHAR(20),
       transactionType VARCHAR(20),
       amount DOUBLE,
       transactionDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
       FOREIGN KEY (accountNo) REFERENCES customer(accountNo)
   );
   ```

## Project Setup

1. Clone the repository:

   ```sh
   git clone https://github.com/GOLLA-SAIRAM/Veltech-bank.git
   ```

2. Import the project into your IDE (Eclipse/IntelliJ IDEA).

3. Add the MySQL JDBC driver to your project classpath.

4. Configure the database connection in the `Database` utility class.

5. Deploy the project to your Apache Tomcat server.

## How to Run

1. Start your MySQL server and Apache Tomcat server.

2. Open a web browser and go to `http://localhost:8080/veltech-bank`.

3. Register a new account or login with existing credentials.

4. Use the application to manage your bank account.

## Directory Structure

```
veltech-bank/
├── src/
│   ├── com/bank/
│   │   ├── CloseAccountServlet.java
│   │   ├── CustomerDAO.java
│   │   ├── Database.java
│   │   ├── DepositServlet.java
│   │   ├── LoginServlet.java
│   │   ├── RegisterServlet.java
│   │   ├── TransactionDAO.java
│   │   ├── WithdrawServlet.java
│   │   └── ... (other classes)
│   └── ... (other packages)
├── web/
│   ├── images/
│   ├── META-INF/
│   ├── WEB-INF/
│   │   ├── web.xml
│   │   └── ... (other configuration files)
│   ├── accountClosed.jsp
│   ├── dashboard.jsp
│   ├── deposit.jsp
│   ├── errorPage.jsp
│   ├── login.jsp
│   ├── register.jsp
│   ├── withdraw.jsp
│   └── ... (other JSP files)
└── README.md
```

## License

This project is licensed under the MIT License.

---

Feel free to modify this README file according to your project's specific details and requirements.
