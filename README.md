# container-orchestration-with-ecs-fargate

Deploy a containerized microservice to Amazon ECS using Fargate with CircleCI as the CI engine.
The example demonstrates build pipelines, image promotion to ECR, and zero-downtime service updates using task definition updates behind an ALB.

## Contents
- `app/` - sample web service (Flask) and Dockerfile
- `infra/` - reference CloudFormation snippets and ECS task definition
- `.circleci/config.yml` - CircleCI pipeline
- `docs/` - deployment notes and architecture diagram

## Highlights
- Builds Docker images in CircleCI, pushes to Amazon ECR.
- Uses ECS service with Fargate launch type and Application Load Balancer for blue/green-style updates.
- IAM task roles used for minimal access to S3 and secrets if required.
- Health checks and CloudWatch metrics included.

## Quick local test
1. Build the image:
   ```bash
   docker build -t sample-web:local app/
   docker run -p 8080:8080 sample-web:local
   ```
2. Open http://localhost:8080

---

Connect with me on LinkedIn: https://www.linkedin.com/in/dhairyashilclouddevops/


---

License: MIT. See LICENSE file.
