# Deployment notes

This repo provides the CI configuration to push images to ECR. A minimal CloudFormation or Terraform template should create:
- ECR repository
- ECS cluster
- ALB with target group and listener rules
- ECS service with Fargate launch type
