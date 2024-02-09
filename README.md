# CI/CD USING GitHub Actions, Terraform, AND ECS TO DEPLOY Laravel-Project

In this project, I deployed a dynamic car rental web application called Rentzone in AWS using GitHub Actions CI/CD pipelines and Terraform for infrastructure deployment.

![Architecture Diagram](images/rentzone.png)

## Terraform Infrastructure as Code
The `iac` directory contains all the required infrastructure terraform files to ensure seamless running of the application. The includes;
- AWS Certificate Manager (acm.tf)
- Application Load Balancer (alb.tf)
- AutoScaling Group (asg.tf)
- Amazon Elastic Container Service (ecs.tf)
- NAT Gateway
- RDS
- Route53
- S3
- Security Groups

## GitHubAction Workflow
The deploy_pipeline.yml file located in the .github/workflows directory constitutes the entire CI/CD pipeline for deploying the application. This pipeline initiates execution immediately upon detecting a commit to the main branch. The following jobs are done by the GitHubAction pipeline; 
- Configure AWS credentials
- Build AWS infrastructure
- Create ECR repository
- Start self-hosted EC2 runner
- Build and push Docker image to ECR
- Create environment file and export to S3
- Migrate data into RDS database with Flyway
- Stop the self-hosted EC2 runner
- Create new task definition revision
- Restart ECS Fargate service
