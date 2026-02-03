🚀 Cloud Infra Learning Lab — AWS EC2 with Terraform

DevOps Internship | Task-2 Submission

Author: Deepak Vishwakarma
Focus: Cloud Infrastructure • Infrastructure as Code • DevOps Foundations
Task: AWS Core Concepts + EC2 (Manual vs Terraform)

📌 Objective

The objective of this task was to:

Understand AWS core compute concepts

Launch an EC2 instance manually using AWS Console

Provision the same EC2 instance using Terraform

Observe the infrastructure lifecycle (create → verify → destroy)

Document the entire process professionally in Markdown

This task focuses on how DevOps engineers manage infrastructure, not just how they click buttons.

🧠 AWS Core Concepts Covered

Before provisioning, I revised and applied the following AWS fundamentals:

EC2 (Elastic Compute Cloud) – Virtual servers in AWS

AMI (Amazon Machine Image) – OS template for instances

Instance Types – Resource sizing (t3.micro – Free Tier)

Key Pairs – Secure SSH authentication

Security Groups – Network firewall rules

Regions & Availability Zones – High availability basics

🛠️ Tools & Technologies

AWS EC2

Terraform v1.14.4

AWS Provider (HashiCorp)

PowerShell (Windows)

Git & GitHub

🖥️ Part 1 — Manual EC2 Launch (AWS Console)
Steps Performed

Opened AWS EC2 Console

Clicked Launch Instance

Selected:

AMI: Ubuntu Server 24.04 LTS

Instance Type: t3.micro (Free Tier)

Created a new key pair

Configured Security Group

SSH (port 22)

HTTP/HTTPS (for learning purposes)

Launched the instance

Verified:

Instance state: Running

Public IP & DNS assigned

Status checks passed

✅ This confirms understanding of manual infrastructure provisioning

⚙️ Part 2 — EC2 Provisioning Using Terraform (IaC)
Why Terraform?

Manual setups don’t scale.

Terraform enables:

Repeatability

Version control

Automation

Clean teardown (destroy)

📂 Project Structure
cloud-infra-learning-lab/
│
├── terraform/
│   ├── provider.tf
│   ├── main.tf
│   └── terraform.lock.hcl
│
└── README.md

🧩 provider.tf
provider "aws" {
  region = "us-east-1"
}

🧩 main.tf
resource "aws_instance" "terraform_ec2" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t3.micro"

  tags = {
    Name = "terraform-ec2-demo"
  }
}

🚀 Terraform Execution Flow
1️⃣ Initialize Terraform
terraform init


✔ Downloads AWS provider
✔ Prepares working directory

2️⃣ Preview Infrastructure
terraform plan


✔ Shows what will be created
✔ No changes applied yet

3️⃣ Create EC2 Instance
terraform apply


✔ EC2 instance created successfully
✔ Verified in AWS Console

4️⃣ Idempotency Check
terraform apply


✔ No changes detected
✔ Confirms desired state matches real state

5️⃣ Destroy Infrastructure (Critical DevOps Step)
terraform destroy


✔ EC2 instance removed
✔ Prevents unnecessary AWS costs
✔ Confirms lifecycle control

🔍 Verification

Terraform-created EC2 visible in AWS Console

Instance details matched Terraform configuration

Instance successfully terminated using IaC

This proves Terraform was the source of truth, not the console.

📸 Screenshot Order

Upload screenshots in this exact order in your repo:

AWS Console – Manual EC2 Running
![Uploading terraform-apply.png…]()


Terraform Init Success

Terraform Plan Output

Terraform Apply (EC2 Created)

AWS Console – Terraform EC2 Visible

Terraform Apply (No Changes)

Terraform Destroy Plan

Terraform Destroy Completed

☁️ DevOps & Cloud Relevance

This task directly supports my Cloud & DevOps journey:

Infrastructure as Code mindset

Understanding mutable vs immutable infrastructure

Clean resource lifecycle management

Cost-aware engineering (destroy unused infra)

Terraform state awareness

DevOps is not about tools — it’s about control, repeatability, and responsibility.

🔮 Future Enhancements

If extended further, I would:

Add variables.tf for reusability

Use Terraform modules

Store state in S3 backend

Add IAM roles for EC2

Integrate GitHub Actions for CI/CD

Provision infra across multiple environments

🎯 Final Reflection

This task was not about launching an EC2 instance.

It was about:

Understanding how infrastructure should be managed

Thinking like a DevOps engineer, not a console user

Proving control over creation, verification, and destruction

I’m excited to build on this foundation and contribute more deeply as part of the internship.
