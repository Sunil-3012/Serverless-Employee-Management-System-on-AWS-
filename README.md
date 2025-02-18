# Serverless Employee Management System on AWS  

## Overview  
Built a **fully serverless web application** that enables users to store and retrieve employee data efficiently using **AWS cloud services**. By leveraging AWS's **serverless architecture**, this project eliminates traditional backend infrastructure, ensuring **high availability, scalability, and cost efficiency**.  

The project integrates **AWS Lambda, DynamoDB, API Gateway, S3, CloudFront, and Route 53** to create a **secure, high-performance web application** while following best practices for **IAM roles, API security, and cloud-based hosting**. 

## Access the Project --> http://d6zi09t4k14ug.cloudfront.net/


## Technologies Used  
- **AWS Lambda** – Serverless compute for backend logic.  
- **Amazon API Gateway** – Exposes RESTful endpoints for CRUD operations.  
- **Amazon DynamoDB** – NoSQL database for employee records.  
- **Amazon S3** – Stores and serves frontend files with static website hosting.  
- **Amazon CloudFront** – Improves frontend performance and security.  
- **Amazon Cognito** – Manages user authentication and sign-ups.  
- **AWS IAM Roles** – Ensures secure access between AWS services.  
- **Amazon Route 53** – Provides a custom domain for the application.  

## Features  
✔ **CRUD operations** (Create, Read, Update, Delete) for employee records.  
✔ **Serverless & scalable** – No server management required.  
✔ **Secure API access** with IAM and Cognito authentication.  
✔ **Efficient frontend delivery** with CloudFront CDN.  
✔ **Custom domain mapping** using Route 53.  

---

## Implementation  

### **1. Created DynamoDB Table**  
- **Table Name:** `employeeData`  
- **Primary Key:** `employeeid`  

### **2. Configured AWS Lambda Functions**  
Implemented two Lambda functions to handle API requests:  
- **getEmployee:** Fetches employee details from DynamoDB.  
- **insertEmployeeData:** Inserts new employee records into DynamoDB.  
- Attached an **IAM Role** to allow Lambda to access DynamoDB.  

### **3. Set Up API Gateway**  
- Created a **REST API (employee)** with two endpoints:  
  - `GET /employee` → Calls `getEmployee` Lambda function.  
  - `POST /employee` → Calls `insertEmployeeData` Lambda function.  
- Enabled **CORS** for cross-origin access.  
- Deployed API and updated **script.js** with the API URL.  

### **4. Hosted Frontend on S3**  
- Uploaded `index.html` and `script.js` to **a public S3 bucket**.  
- Enabled **static website hosting** on S3.  
- Configured **S3 Bucket Policy** to allow public access:  
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::serverlessproject-own/*"
      }
    ]
  }


## Outcome
- Successfully deployed a serverless, **auto-scaling employee management system.

- Eliminated server maintenance while ensuring secure and efficient data handling.

- Optimized frontend performance using **CloudFront and **Route 53.

- Implemented Cognito authentication for secure user access.




