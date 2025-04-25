
# 🚀 Strapi Deployment on AWS ECS Fargate with Terraform & GitHub Actions

This project deploys a Strapi CMS application on **Amazon ECS Fargate**, fully automated using **Docker**, **Terraform**, **GitHub Actions**, and **Amazon CloudWatch**. The infrastructure includes networking (VPC, subnets, IGW), ECS cluster, ALB, ECR for container image hosting, and CloudWatch for monitoring.

---

## 📦 Project Structure
- `terraform/`: Infrastructure as Code
- `docker/`: Dockerfile for Strapi
- `.github/workflows/`: GitHub Actions CI/CD

---

## 🔧 Infrastructure Components

- **VPC with Public Subnets**
- **Internet Gateway (IGW)** and **Route Table**
- **Application Load Balancer (ALB)** with Security Group
- **ECS Cluster** (Fargate)
- **Amazon ECR** for Docker image storage
- **Security Groups** for ALB and ECS Tasks
- **IAM Roles** for ECS Task Execution
- **Amazon CloudWatch**:
  - Log group for ECS task logging
  - CPU utilization alarms for ECS services

---

## ⚙️ GitHub Actions Workflow

**Triggered on push to `main` branch:**

### Steps:
1. Checkout the repo
2. Set up Docker
3. Configure AWS credentials
4. Create ECR repo if it doesn’t exist
5. Build & push Docker image to ECR
6. Set up Terraform
7. Run `terraform init` and `terraform apply`
8. Wait 10 minutes and run `terraform destroy` (optional for demo)

---

## 💡 Tools Used
- **Terraform**: `1.6+`
- **AWS ECS Fargate**
- **Strapi CMS**
- **Amazon CloudWatch**
- **GitHub Actions**
