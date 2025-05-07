# 🛒 Fullstack E-Commerce Project

Welcome to the Fullstack E-Commerce Shopping Project repository! This project is a comprehensive e-commerce application built using **React.js** for the frontend and **Spring Boot** for the backend. It aims to deliver a seamless online shopping experience with features like product browsing, cart management, and order processing.

---

## 🛠️ Technologies Used

### Frontend
- **Framework**: React.js
- **State Management**: Redux
- **Styling**: Tailwind CSS
- **HTTP Client**: Axios

### Backend
- **Framework**: Spring Boot
- **Security**: Spring Security
- **Database Access**: Spring Data JPA

### Other Tools
- **Database**: PostgreSQL
- **Authentication**: JWT (JSON Web Tokens)
- **Payment Gateway**: Stripe/PayPal (Optional)
- **Build Tools**: Maven, Webpack

---

## 🚀 Features

### User Features
- **User Authentication**: Secure login and registration using JWT.
- **Product Browsing**: View and search for products.
- **Cart Management**: Add, update, and remove items from the cart.
- **Order Processing**: Place orders and track their status.

### Admin Features
- **Admin Dashboard**: Manage products, orders, and users.
- **Product Management**: Add, update, and delete products.
- **Order Management**: View and update order statuses.

### Additional Features
- **Payment Integration**: Secure payment processing with Stripe/PayPal.

---

## 🛠️ Getting Started

### Prerequisites
Before you begin, ensure you have the following installed:
- **Node.js** (v16+)
- **Java** (JDK 11+)
- **PostgreSQL**
- **Maven**

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/NematSiddique/e-comm.git
   cd e-comm
   ```

2. **Set Up the Backend**
   - Navigate to the `backend/` directory.
   - Configure the `application.properties` file with your PostgreSQL credentials.
   - Run the following command to build and start the backend:
     ```bash
     mvn spring-boot:run
     ```

3. **Set Up the Frontend**
   - Navigate to the `UI/` directory.
   - Install dependencies:
     ```bash
     npm install
     ```
   - Start the development server:
     ```bash
     npm start
     ```

4. **Database Setup**
   - Run the database migration scripts to set up the required tables.

---

## 📂 Project Structure

```
e-comm/
├── UI/       # React.js application
├── backend/        # Spring Boot application
└── README.md       # Project documentation
```
