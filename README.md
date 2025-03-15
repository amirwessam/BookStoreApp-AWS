# AWS Web Application Hosting

This repository contains a project focused on designing and implementing a web application hosted on AWS. The project leverages various AWS services, including EC2, Lambda functions, Elastic Load Balancing (ELB), and DynamoDB, to ensure high availability, scalability, and efficient data management.

## Project Overview

The primary objective of this project is to create a simple web application using a JavaScript stack (substituting MongoDB with DynamoDB), and host it on AWS. The architecture is designed to provide high availability across multiple EC2 instances, manage image uploads using S3, and perform image resizing with Lambda functions.

## Features

- **EC2 Instances**: Host the web application on multiple EC2 instances for high availability.
- **Elastic Load Balancer (ELB)**: Distribute incoming traffic across multiple EC2 instances to ensure reliability and performance.
- **DynamoDB**: Use DynamoDB for scalable and managed NoSQL database operations.
- **Lambda Functions**: Implement serverless functions for image resizing and other background tasks.
- **S3**: Store and manage image uploads in S3 buckets.
- **AWS SDK**: Interact with various AWS services programmatically.
- **Docker**: Containerize the application for consistent deployment.

## Getting Started

To get started with the project, follow the steps below:

### Prerequisites

- AWS account with access to EC2, S3, DynamoDB, Lambda, and ELB services.
- Node.js and npm installed on your local machine.
- Docker installed on your local machine.

### Setup Instructions

1. **Clone the Repository**
    ```bash
    git clone https://github.com/amirwessam/BookStoreApp-AWS.git
    cd BookStoreApp-AWS
    ```

2. **Install Dependencies**
    ```bash
    npm install
    ```

3. **Set Up AWS Resources**
    - **EC2 Instances**: Launch multiple EC2 instances and deploy the web application.
    - **ELB**: Set up an Elastic Load Balancer to distribute traffic across EC2 instances.
    - **DynamoDB**: Create a DynamoDB table for your application data.
    - **S3 Buckets**: Create S3 buckets for storing images.
    - **Lambda Functions**: Create Lambda functions for image resizing and configure S3 triggers.

4. **Configure AWS SDK**
    - Update the `config.js` file with your AWS credentials and resource details.

    ```javascript
    module.exports = {
        aws: {
            region: 'your-region',
            accessKeyId: 'your-access-key-id',
            secretAccessKey: 'your-secret-access-key',
            s3Bucket: 'your-s3-bucket-name',
            dynamoDBTable: 'your-dynamodb-table-name'
        }
    };
    ```

5. **Dockerize the Application**
    - Build the Docker image:

    ```bash
    docker build -t your-image-name .
    ```

    - Run the Docker container:

    ```bash
    docker run -p 3000:3000 your-image-name
    ```

6. **Deploy the Application**
    - Push the Docker image to a container registry (e.g., Amazon ECR).
    - Deploy the Docker containers on your EC2 instances.

7. **Run the Application**
    - Access the web application through the ELB endpoint.
