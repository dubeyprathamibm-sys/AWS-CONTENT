

# 🚀 AWS EC2 DevOps Deep Dive – AMI, Auto Scaling, Load Balancer & Launch Template

---

## 🧱 1. EC2 AMI (Amazon Machine Image)

### 📘 What is an AMI?
An **AMI** is a pre-configured template containing an OS and software used to launch new EC2 instances. You can create custom AMIs for consistent environments, faster provisioning, and scaling.

---

### 🛠️ **Steps to Create a Custom AMI**

#### 🔧 Step 1: Launch and Configure EC2 Instance
- Launch a t2.micro EC2 instance (Amazon Linux or Ubuntu)
- SSH into it and install your software, e.g.:
```bash
sudo yum update -y
sudo yum install httpd -y
```

#### 🧪 Step 2: Test the Configuration
- Start and verify services
```bash
sudo systemctl start httpd
```

#### 📷 Step 3: Create an AMI from EC2
- Go to EC2 Dashboard → Instances → Select your instance → **Actions > Image > Create Image**
- Enter a name (e.g., `webserver-ami-v1`)
- Click **Create Image**

#### ⏱️ Step 4: Wait for the AMI to be available
- Go to **AMIs** section and monitor status
- Use this AMI in Launch Templates or Auto Scaling

---

## ⚙️ 2. Auto Scaling Group (ASG)

### 📘 What is Auto Scaling?
**Auto Scaling** automatically launches or terminates EC2 instances based on demand (CPU, time, load balancer, etc.), ensuring performance and cost-efficiency.

---

### 🛠️ **Steps to Create Auto Scaling Group**

#### 🧱 Prerequisites:
- A **Launch Template** or a **Launch Configuration**
- A **Custom AMI** (optional)
- A **Load Balancer** (optional)

---

### 👣 Step-by-Step Setup

#### ✅ Step 1: Go to EC2 → **Auto Scaling Groups**
- Click **Create Auto Scaling Group**

#### ✅ Step 2: Choose Launch Template
- Select an existing **Launch Template** (see section 4 below)

#### ✅ Step 3: Configure Group
- Name: `my-auto-scale-group`
- Network: Select a VPC and public subnets

#### ✅ Step 4: Attach Load Balancer (Optional)
- Select an existing **Application Load Balancer** (see section 3)

#### ✅ Step 5: Set Desired, Min, Max Capacity
- Desired: 1  
- Min: 1  
- Max: 3  

#### ✅ Step 6: Add Scaling Policies
- Policy Type: **Target Tracking**
- Metric: **Average CPU Utilization**
- Target: 50% CPU

#### ✅ Step 7: Review and Create

---

## 🌐 3. Load Balancer (Application Load Balancer - ALB)

### 📘 What is ALB?
An **Application Load Balancer (ALB)** distributes incoming traffic across multiple EC2 instances, ensuring high availability and fault tolerance.

---

### 🛠️ **Steps to Create an ALB**

#### ✅ Step 1: Go to EC2 → Load Balancers → **Create Load Balancer**
- Choose **Application Load Balancer**
- Name: `my-app-lb`
- Scheme: **Internet-facing**
- IP type: IPv4

#### ✅ Step 2: Configure Listeners
- Listener: HTTP (port 80)

#### ✅ Step 3: Availability Zones
- Choose **VPC** and **2 subnets**

#### ✅ Step 4: Security Group
- Create or choose a group that allows HTTP (port 80)

#### ✅ Step 5: Create a Target Group
- Target type: **Instance**
- Name: `web-target-group`
- Protocol: HTTP, Port: 80

#### ✅ Step 6: Register Targets
- Choose running EC2 instances or skip (Auto Scaling can attach later)

#### ✅ Step 7: Review and Create

---

## 📦 4. EC2 Launch Template

### 📘 What is a Launch Template?
A **Launch Template** defines configuration for EC2 instances like AMI, instance type, key pair, and security groups. Used in Auto Scaling, EC2 Fleet, and Spot Requests.

---

### 🛠️ **Steps to Create a Launch Template**

#### ✅ Step 1: Go to EC2 → **Launch Templates** → Create template
- Name: `webserver-template`
- Description: `Base template for auto scaling group`

#### ✅ Step 2: Source Template (Optional)
- Leave as blank if this is the first template

#### ✅ Step 3: Launch Template Content
- AMI: Select a custom or public AMI
- Instance type: t2.micro
- Key pair: Choose an existing `.pem` file
- Security group: Allow SSH (22) and HTTP (80)

#### ✅ Step 4: User Data (Optional Script)
```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
echo "Hello from EC2 Auto Scaling" > /var/www/html/index.html
```

#### ✅ Step 5: Create Template

You can now reuse this template in:
- Manual launches
- Auto Scaling Groups
- Spot Fleet Requests

---

## 🔁 Combined Use Case: Scalable Web App

1. ✅ Launch EC2 and install Apache  
2. ✅ Create a Custom AMI  
3. ✅ Create a Launch Template using that AMI  
4. ✅ Setup an Application Load Balancer  
5. ✅ Configure Auto Scaling Group using the Launch Template + ALB  
6. ✅ Access your public ALB DNS to view the web page  
7. ✅ Watch instances scale automatically when CPU threshold is crossed

---

## 🎯 DevOps Best Practices

| Task | Tool |
|------|------|
| Infrastructure Setup | Terraform / CloudFormation |
| Provisioning | Ansible / Packer |
| Monitoring | CloudWatch, Datadog |
| Security | IAM, Security Groups, KMS |
| Automation | CI/CD with CodeDeploy / Jenkins on EC2 |
| Cost Optimization | Spot Instances + Auto Scaling |

---
