This is a real-time AWS full-stack DevOps project setup (React + Node.js + MySQL with CI/CD using AWS CodePipeline, CodeBuild, and CodeDeploy). The flow is:

Infra Setup (VPC, Subnets, NAT, IGW, Route Tables, SGs, Bastion) → to build a secure, multi-tier network.

RDS MySQL → backend DB tier in private subnets.

Application Tier (Node.js) → private subnets, behind an internal ALB, deployed via ASG.

Web Tier (Nginx/React) → public entry point, ASG + external ALB.

CI/CD → Backend & frontend pipelines using GitHub → CodeBuild → CodeDeploy → EC2.

Monitoring/Secrets → CloudWatch + SSM Parameter Store + S3 for artifacts.

Validation & Cleanup → check external ALB, then delete resources to save cost.
