
# 🚀 Terraform Project

## 📘 Overview
> This project uses **Terraform** to manage and provision infrastructure as code.  
> It's designed to be **modular**, **reusable**, and **scalable**.

Includes:
- 🧱 VPC (Virtual Private Cloud)
- 🌐 Public Subnets
- 🔐 Private Subnets
- 💻 EC2 Instances
- ⚙️ TDS (Custom Module - e.g., database or internal app)

---

## 📁 Project Structure

```bash
terraform_project/
│
├── main.tf             # 🌍 Core Terraform logic
├── provider.tf         # ☁️ Provider setup (e.g., AWS)
├── variable.tf         # 🔧 Input variables
│
└── moduals/            # 📦 Reusable Modules
    ├── ec2/            # 💻 EC2 Module
    ├── vpc/            # 🧱 VPC Module
    ├── private_subnet/ # 🔐 Private Subnet
    ├── public_subnet/  # 🌐 Public Subnet
    └── tds/            # ⚙️ TDS Module (Custom/Service)
```
## 🔧 Modules Breakdown

### 🧱 VPC Module (`moduals/vpc`)
- Creates the VPC  
- Configures routing tables  
- Adds Internet & NAT gateways

### 🌐 Public Subnet (`moduals/public_subnet`)
- Adds public subnets to the VPC  
- Attaches them to the Internet Gateway

### 🔐 Private Subnet (`moduals/private_subnet`)
- Secure subnets with **no internet access**  
- Typically used for databases or backend servers

### 💻 EC2 Module (`moduals/ec2`)
- Launches EC2 instances  
- Set AMI, instance type, key pair, and security groups

### ⚙️ TDS Module (`moduals/tds`)
- Custom service logic (e.g., internal tool or database)  
- Automates setup and provisioning

### 🧩 Step 1: 📥 Clone the Repository

```bash
# 📦 Clone the GitHub repository to your local machine
git clone https://github.com/Mohamed2107/terraform_project.git

# 📁 Navigate into the project directory
cd terraform_project
```

### ⚙️ Step 2: 🚀 Initialize Terraform
```bash
# 🔧 Initialize the Terraform working directory
terraform init
```
- 📥 This will download all required provider plugins.
- ⚙️ Sets up the Terraform backend (if configured).
### 🛠️ Step 3: 📝 Set Your Variables
. 🧾 Modify variable.tf or create a terraform.tfvars file with your desired values.
```bash
# Example terraform.tfvars content
vpc_cidr           = "10.0.0.0/16"
instance_type      = "t2.micro"
availability_zones = ["us-east-1a", "us-east-1b"]
```
### 🔍 Step 4: 🧪 Review the Terraform Plan
```bash
# 🔎 Preview the changes Terraform will make
terraform plan
```
- ✅ This will show what will be created or modified without making actual changes.
### 🚀 Step 5: ✅ Apply the Configuration
```bash
# 🚀 Deploy your infrastructure
terraform apply
```
- 🆗 You’ll be asked to confirm the changes. Type yes to proceed.

- 🏗️ Terraform will start provisioning the infrastructure.
## 💡 Why Use Modules?

| ✅ Feature      | 🔎 Description                                                                 |
|-----------------|-------------------------------------------------------------------------------|
| ♻️ Reusability  | Use the same logic across multiple environments or projects                   |
| 🧹 Maintainability | Isolated module logic simplifies updates and troubleshooting                |
| 📈 Scalability   | Easily extend infrastructure without rewriting everything                    |
