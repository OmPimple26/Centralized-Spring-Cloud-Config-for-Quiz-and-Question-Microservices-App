# ⚙️ Centralized Spring Cloud Config Repository for Quiz & Question Microservices 🚀

This repository serves as the centralized configuration hub 🧠 for the Spring Boot Microservices – Quiz & Question App. It is consumed by a Spring Cloud Config Server ⚙️ to provide externalized, version-controlled, and centralized configuration management across all microservices, ensuring scalability, consistency, and easy maintenance 🚀

---

## 🧠 Why Spring Cloud Config?

Spring Cloud Config allows you to:

* Centralize application configuration 📦
* Avoid hardcoding properties inside microservices
* Change configuration **without rebuilding services**
* Maintain **environment-specific configs**
* Follow **real-world microservices best practices**

---

## 🏗️ Architecture Overview

```
Microservices  ──▶  Config Server  ──▶  This Git Repository
   (Quiz / Question / Gateway)
```

* All services fetch configuration from **Config Server**
* Config Server pulls data from **this Git repository**
* Configuration is shared, versioned, and reusable

---

## 📂 Repository Structure

```
spring-cloud-config-repo
├── application.properties
├── API-GATEWAY.properties
├── QUIZSERVICE.properties
└── QUESTIONSERVICE.properties
```

---

## 📄 Configuration Files Explained

### 🔹 `application.properties`

* Common configuration shared across all services
* Eureka-related defaults

```
eureka.client.service-url.defaultZone=http://localhost:8761/eureka/
eureka.instance.prefer-ip-address=true
eureka.instance.hostname=localhost
```

---

### 🔹 `API-GATEWAY.properties`

* API Gateway configuration
* Port, routing, and Eureka-based discovery

Key features:

* Dynamic routing using Eureka
* Supports uppercase service IDs

---

### 🔹 `QUIZSERVICE.properties`

* QuizService-specific configuration
* MySQL database connection
* JPA & Hibernate settings
* Eureka registration

---

### 🔹 `QUESTIONSERVICE.properties`

* QuestionService-specific configuration
* MySQL database connection
* JPA & Hibernate settings
* Eureka registration

---

## 🔗 Related Main Microservices Repository

👉 **Spring Boot Microservices – Quiz & Question App**
[https://github.com/OmPimple26/Spring-Boot-Microservices-Quiz-and-Question-App](https://github.com/OmPimple26/Spring-Boot-Microservices-Quiz-and-Question-App)

This config repo is **exclusively used** by that project.

---

## 🚀 How It Works (Flow)

1. Config Server starts (`port: 8888`)
2. Config Server clones this Git repository
3. Microservices request configs using:

   ```
   spring.config.import=optional:configserver:http://localhost:8888
   ```
   
4. Config Server serves the correct `.properties` file
5. Services start with centralized configuration

---

## 🛠️ Technologies Used

* Spring Cloud Config 📦
* Git & GitHub 🌍
* Spring Boot 3.2.5
* Eureka Discovery
* MySQL
* Maven

---

## 🎯 Ideal For Learning

This repository is perfect for:

* Beginners learning Spring Cloud Config
* Understanding centralized configuration
* Microservices architecture practice

---

## ⭐ Contribution & Usage

* Fork 🍴
* Clone 🧑‍💻
* Modify configs
* Connect with your own Config Server

Feel free to open issues or suggest improvements 🚀

---

### 🔥 Built for real-world Microservices learning

Happy Coding! 💻✨
