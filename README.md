# CI/CD USING GitHub Actions, Terraform, AND ECS TO DEPLOY Laravel-Project

In this project, I deployed a dynamic car rental web application called Rentzone in AWS using GitHub Actions CI/CD pipelines and Terraform for infrastructure deployment.

![Architecture Diagram](images/rentzone.png)

## Terraform Infrastructure as Code
The `iac` directory contains all the required infrastructure terraform files to ensure seamless running of the application. The includes;
- AWS Certificate Manager (acm.tf) - Application Load Balancer (alb.tf) - AutoScaling Group (asg.tf) - Amazon Elastic Container Service (ecs.tf) - NAT Gateway - RDS - Route53 - S3 - Security Groups
