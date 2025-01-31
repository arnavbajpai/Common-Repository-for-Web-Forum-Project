# Web Forum Powered by AWS: Overview

This repository provides an overview, architecture, and setup instructions for the web forum project, along with links to the individual repositories for the frontend, backend, and database.

## Project Repositories
- [Backend Repository](https://github.com/arnavbajpai/Web-Forum-powered-by-AWS-Backend-REST-API): Developed using GoLang and deployed on AWS Lambda and API Gateway.
- [Frontend Repository](https://github.com/arnavbajpai/Web-Forum-powered-by-AWS-Frontend): Built with React.js and hosted on AWS S3.
- [Database Repository](https://github.com/arnavbajpai/Web-Forum-powered-by-AWS-Backend-REST-API): Built on MySQL, hosted on AWS RDS.

## Features

The web forum provides the following functionality: 

1. User authentication using Google ID and auto-registration at first login. 
2. The forum is extensible, but the deployed version supports the following categories: Food, Games, Movies, Musics, Sports, Tech. 
3. Users can start discussion on new topics, under these categories. They can post comments on existing topics, edit posts, and respond to comments from other users.  

## Live Demonstration

[AWS hosted implementation](https://d173h28cgmmekf.cloudfront.net/)

(You will need a google account to test. Only non-sensitive information is requested from google. To remove app access to the Google account, you can go to the Google Account's third-party connections page and delete the connection.)  

## Project Architecture
The Web Forum application is designed as a scalable and modular system, leveraging modern cloud technologies.

![Architecture Diagram](docs/architecture-diagram%20(1).png)

- **Backend**: RESTful API implementation using GoLang.
- **Frontend**: A responsive user interface developed with React.js.
- **Database**: Structured storage in MySQL for users, threads, and posts.
- **Authentication**: Secure Google-based login powered by AWS Cognito User Pools. 
- **Cloud Deployment**:
  - AWS S3 and CloudFront: The website, hosted on S3, is exposed through CloudFront for improved performance and security, with AWS WAF providing additional protection against web threats.
  - AWS Lambda and API Gateway: The API is built using AWS Lambda and exposed via API Gateway, enabling serverless, scalable, and secure request handling. API Gateway performs authorizes requests based on JWT token issued by Cognito service.  
  - AWS RDS: The application uses MySQL hosted on Amazon RDS, ensuring managed, scalable, and high-performance database storage.

## Deployment and Configuration Instructions
The three project repositories linked above, provide instructions for building, installing, deploying the 3 components of the solution. In addition the following generic instructions will help in making the process of installation and testing more seamless. 

### 1. Deployment Options
- The project supports both **local and AWS deployments** for its three core components: **Frontend, Backend, and Database**.
- **Important:** All components **must** be deployed **either locally or on AWS**—a mixed deployment is not supported.
- The **preferred deployment method is AWS**, as it offers better security. **Local deployment is supported solely for testing purposes.**

### 2. User Authentication
- **Amazon Cognito is used for authentication in both local and AWS deployments.**
- Even when running locally, authentication still relies on Cognito, ensuring consistency with the cloud environment.

### 3. Backend and Database Configuration
- The **backend must be configured to access the database** in both deployment scenarios.
- **Local Deployment:** Database connection parameters must be manually set within the code.
- **AWS Deployment:** Database access is configured using **Lambda environment variables** and requires proper **networking and security settings**.

### 4. API Authentication & Authorization
- **Authentication and authorization for APIs rely on Amazon API Gateway**, which is **only available in AWS deployments**.
- In **local deployment**, API authorization is bypassed by assigning a **test user context** to facilitate testing.


## Contact
If you have questions or suggestions, feel free to reach out at [arnavbcool@gmail.com](mailto:arnavbcool@gmail.com).
