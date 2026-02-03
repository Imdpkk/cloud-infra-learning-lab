☁️ Task-2: AWS EC2 Provisioning — Manual & Terraform (IaC)

DevOps Internship | Cloud Infrastructure Fundamentals
Author: Deepak Vishwakarma
Role: Aspiring Cloud & DevOps Engineer
Repository: https://github.com/Imdpkk/cloud-infra-learning-lab

🚀 Overview

This repository documents Task-2 of my DevOps Internship, where I explored AWS EC2 fundamentals and Infrastructure as Code (IaC) using Terraform.

The task was designed to evaluate not just execution, but also:

Cloud fundamentals understanding

Automation mindset

Infrastructure lifecycle awareness

Clean documentation & version control practices

This project demonstrates both manual and automated cloud provisioning, which is essential for real-world DevOps workflows.

🎯 Task Objective

✔ Learn AWS core compute concepts
✔ Launch an EC2 instance manually via AWS Console
✔ Provision an EC2 instance using Terraform
✔ Validate infrastructure state and idempotency
✔ Safely destroy cloud resources
✔ Document the entire workflow professionally

🧰 Tech Stack & Tools
Category	Tools
Cloud Platform	AWS (EC2)
IaC Tool	Terraform
OS	Ubuntu Linux
CLI	PowerShell
Version Control	Git & GitHub
🧱 Part 1 — Manual EC2 Instance Launch (AWS Console)
What I Did

Logged into AWS Management Console

Navigated to EC2 → Launch Instance

Selected Ubuntu Server 24.04 LTS

Chose t3.micro (Free Tier eligible)

Created a secure SSH key pair

Configured a security group allowing SSH (port 22)

Launched the instance and verified its state

What I Learned

How AMIs, instance types, and key pairs work together

Security group basics and public IP assignment

Manual provisioning helps understand cloud internals before automation

⚙️ Part 2 — EC2 Provisioning Using Terraform (IaC)

This section demonstrates how the same infrastructure can be created using code.

Terraform Configuration
provider.tf
provider "aws" {
  region = "us-east-1"
}

main.tf
resource "aws_instance" "terraform_ec2" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t3.micro"

  tags = {
    Name = "terraform-ec2-demo"
  }
}

▶️ Terraform Workflow Executed
terraform init


✔ Initialized Terraform and installed AWS provider

terraform plan


✔ Previewed the infrastructure changes before creation

terraform apply


✔ EC2 instance successfully created via Terraform

terraform apply


✔ Re-run confirmed idempotency (no changes required)

terraform destroy


✔ Cleanly destroyed the infrastructure to avoid cost

📸 Screenshots & Proof of Work

All screenshots are stored inside:

screenshots/task-2/

Screenshot Flow (Recommended Viewing Order)

Manual EC2 instance running in AWS

Terraform initialization success

Terraform plan output

Terraform apply (instance creation)

EC2 instance visible in AWS Console

Terraform apply → No changes

Terraform destroy plan

Terraform destroy completed

This sequence clearly shows the full lifecycle of cloud infrastructure.

🧠 Key Learnings

Through this task, I gained hands-on experience with:

AWS EC2 architecture & lifecycle

Infrastructure as Code fundamentals

Terraform state, plan, apply & destroy

Idempotent infrastructure behavior

Cloud cost awareness and cleanup

Bridging manual cloud actions with automation

☁️ Why This Matters for Cloud & DevOps

This task reflects real DevOps thinking:

Manual setup builds conceptual clarity

Terraform enables automation & scalability

Version-controlled infrastructure improves reliability

Destroying resources shows cost responsibility

You can’t automate what you don’t understand —
this task helped me understand before automating.

🔮 Future Enhancements

If extended further, I would:

Use Terraform variables & outputs

Store Terraform state remotely (S3 + DynamoDB)

Create security groups using Terraform

Add CI/CD with GitHub Actions

Deploy workloads on the EC2 instance

Extend to multi-environment setups (dev/stage/prod)

🧾 Final Note

This repository is not just a task submission —
it represents my approach to learning Cloud & DevOps:

✔ Learn fundamentals deeply
✔ Automate responsibly
✔ Document clearly
✔ Think like a production engineer

I’m excited to continue growing and contributing as part of this DevOps journey 🚀

👤 About Me

Deepak Vishwakarma
Cloud & DevOps Enthusiast
GitHub: https://github.com/Imdpkk
