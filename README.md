# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!

---

## Project Structure & Added Files
To containerize the application, a `Dockerfile` was added to each of the four microservice directories, alongside the orchestration configuration inside the `Microservices` folder and proof screenshots at the root:

```text
Microservices-Task/
├── .gitignore
├── LICENSE
├── README.md
├── Microservices/
│   ├── docker-compose.yml       # Orchestrates all 4 services and creates a shared bridge network
│   ├── gateway-service/
│   │   ├── Dockerfile           # Uses node:18-alpine, installs dependencies, exposes port 3003
│   ├── order-service/
│   │   ├── Dockerfile           # Uses node:18-alpine, installs dependencies, exposes port 3002
│   ├── product-service/
│   │   ├── Dockerfile           # Uses node:18-alpine, installs dependencies, exposes port 3001
│   └── user-service/
│       ├── Dockerfile           # Uses node:18-alpine, installs dependencies, exposes port 3004
└── screenshots/
    ├── 1.png                    # Successful container build logs
    ├── 2.png                    # Active running containers (docker ps)
    ├── 3001.png                 # Product-service running in browser
    ├── 3002.png                 # Order-service running in browser
    ├── 3003.png                 # Gateway-service running in browser
    └── 3004.png                 # User-service running in browser
