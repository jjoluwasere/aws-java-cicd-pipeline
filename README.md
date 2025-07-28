# ☁️ Java Web App on AWS EC2 with CI/CD Pipeline

This repository demonstrates the deployment of a **Java-based web application** on AWS EC2, showcasing how to provision infrastructure, configure the environment, and set up a fully automated CI/CD pipeline.

---

## Overview
This project covers:
- Deploying a **Java web application** on an **Amazon EC2** instance  
- Setting up **Maven** for building and managing dependencies  
- Configuring **Apache HTTPD** as a reverse proxy for Tomcat  
- Implementing a **CI/CD pipeline** using AWS services  
- Following **cloud deployment best practices**

---

## Tech Stack
- **Java 8** – Core language for the application  
- **Apache Tomcat** – Application server for running the WAR file  
- **Apache HTTPD** – Reverse proxy for serving traffic on port 80  
- **Maven** – Build tool and dependency management  
- **AWS EC2** – Hosting the application  
- **AWS CodePipeline / CodeBuild / CodeDeploy** – CI/CD automation  
- **CloudFormation** – Infrastructure as Code for provisioning

---

## 📐 Architecture

1. **Developer pushes code** to GitHub  
2. **AWS CodePipeline** triggers a new pipeline run  
3. **AWS CodeBuild**:
   - Installs dependencies (Java, Maven)
   - Compiles the project
   - Packages a `.war` file  
4. **AWS CodeDeploy**:
   - Stops running services
   - Deploys the `.war` to Tomcat
   - Restarts services  
5. **Apache HTTPD** reverse proxies requests from **port 80** to Tomcat on **port 8080**
