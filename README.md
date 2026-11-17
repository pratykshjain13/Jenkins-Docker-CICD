# Docker-Based CI/CD Pipeline Using Jenkins, GitHub & Docker Compose

## Project Overview
Implemented an automated CI/CD pipeline using Jenkins, GitHub, Docker and Docker Compose on a RHEL Linux server.

The pipeline automatically checks out source code, builds a Docker image, tests the web application and deploys the application using Docker Compose.

## Technologies Used
- RHEL Linux
- Git & GitHub
- Jenkins
- Docker
- Docker Compose
- Apache HTTP Server
- Shell Scripting
- Jenkinsfile (Declarative Pipeline)

## CI/CD Workflow
1. Checkout source code from GitHub.
2. Build Docker image using Docker Compose.
3. Start the application container and test it using curl.
4. Deploy the application using Docker Compose.
5. Verify the running container and application.

## Application Details
- Docker Image: `webapp:v1`
- Compose Container: `webapp2`
- Application Port: `8083`
- Web Server: Apache HTTP Server

## Key Learnings
- Integrated Jenkins with GitHub and Docker.
- Created a Declarative Jenkins pipeline.
- Automated Docker image building.
- Tested application availability using curl.
- Managed application containers using Docker Compose.
- Deployed a web application on a RHEL server.

## Project Result
Successfully implemented and executed the CI/CD pipeline with all four stages: Checkout, Build, Test and Deploy.

## Repository
https://github.com/pratykshjain13/project-1
