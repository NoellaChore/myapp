# AWS CI/CD Capstone Project

This repository contains a Node.js web application and AWS configuration files for a full CI/CD pipeline using CodePipeline, CodeBuild, CodeDeploy, ECR, and ECS.

## Architecture

- **Source:** GitHub repository (Node.js Express app)
- **Build:** AWS CodeBuild compiles the app, runs unit tests, and builds a Docker image
- **Artifact Storage:** Docker image is pushed to Amazon ECR
- **Deploy:** AWS ECS (Fargate) runs the containerized application
- **Orchestration:** AWS CodePipeline ties all stages together
- **Monitoring:** CloudWatch alarms monitor ECS service health
- **Load Balancer:** Application Load Balancer routes traffic to ECS

## Live App URL

http://myapp-alb-497114209.us-east-1.elb.amazonaws.com

## Steps to Reproduce

1. Push code to GitHub
2. CodePipeline fetches source and triggers CodeBuild
3. CodeBuild runs tests, builds Docker image, pushes to ECR
4. CodeDeploy updates ECS service with new image
5. ECS service serves app behind Application Load Balancer

## Project Structure