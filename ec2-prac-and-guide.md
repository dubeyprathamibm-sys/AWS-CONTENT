
# 📘 AWS EC2 DevOps Guide – Practical + Interview Ready

---

## 🖥️ What is Amazon EC2?

**Amazon EC2 (Elastic Compute Cloud)** is a core AWS service that allows users to provision virtual machines in the cloud. It provides scalable, pay-as-you-go compute capacity, helping developers, sysadmins, and DevOps engineers deploy applications without managing physical hardware.

- ☁️ **Service Type:** Infrastructure as a Service (IaaS)  
- 🧠 **Use Cases:** Web hosting, CI/CD servers (Jenkins), microservice deployment, container hosting, etc.  
- 💸 **Free Tier:** 750 hours/month for 12 months with t2.micro or t3.micro instance

---

## ⚙️ Step-by-Step: Launch an EC2 Instance (Free Tier)

### 1. 🧭 **Sign in to AWS Console**
- Go to [https://console.aws.amazon.com](https://console.aws.amazon.com)

### 2. 🚀 **Launch an Instance**
- Go to **EC2 Dashboard** → Click **Launch Instance**
- Name your instance (e.g., `DevOpsTestVM`)

### 3. 🖥️ **Choose AMI**
- Select **Amazon Linux 2023** or **Ubuntu 22.04 LTS**

### 4. 📐 **Choose Instance Type**
- Choose **t2.micro** or **t3.micro** (Free Tier eligible)

### 5. 🔐 **Create Key Pair**
- Download the `.pem` key for SSH access

### 6. 🔐 **Configure Security Group**
- Allow **SSH (port 22)** for your IP  
- Allow **HTTP (port 80)** for web traffic (if needed)

### 7. 🎯 **Launch**
- Click **Launch Instance**
- Wait until it says `running`

### 8. 🧑‍💻 **Connect via SSH**
```bash
chmod 400 my-key.pem
ssh -i "my-key.pem" ec2-user@<Public-IP>
```

(Use `ubuntu@` for Ubuntu AMIs)

### 9. 📦 **Install Software (e.g., Apache)**
Amazon Linux:
```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
```

Ubuntu:
```bash
sudo apt update
sudo apt install apache2 -y
sudo systemctl start apache2
```

Visit `http://<Public-IP>` to see the default web page.

### 10. 🛑 **Stop or Terminate the Instance**
- **Stop**: Saves the machine state  
- **Terminate**: Deletes the instance and volume

---

## 🧠 DevOps Interview Questions & Answers on EC2

### ✅ 1. What is EC2 and why is it important in DevOps?
**Answer:**  
Amazon EC2 provides resizable compute capacity in the cloud. In DevOps, it is essential for hosting CI tools, automation scripts, and scalable apps without worrying about underlying hardware. It supports rapid provisioning using IaC tools like Terraform.

---

### ✅ 2. How do you provision EC2 in automation workflows?
**Answer:**  
Provisioning can be automated using **Terraform**, **CloudFormation**, or **Ansible**. A pipeline typically involves IaC to launch the instance, configure it using scripts or Ansible, and register it for further tasks.

---

### ✅ 3. What is an AMI and how is it used in CI/CD?
**Answer:**  
AMI (Amazon Machine Image) is a snapshot of an OS with pre-installed software. DevOps teams use custom AMIs to speed up provisioning in CI/CD pipelines, ensuring environment consistency.

---

### ✅ 4. How does EC2 integrate with other AWS services?
**Answer:**  
EC2 integrates with:
- **S3** (artifact storage)  
- **IAM** (secure access)  
- **CloudWatch** (monitoring)  
- **CodeDeploy** (automated deployments)  
This builds a powerful automation ecosystem.

---

### ✅ 5. How is security managed in EC2?
**Answer:**  
- **Security Groups** control traffic  
- **Key Pairs** enable SSH  
- **IAM Roles** secure access to AWS APIs  
- **VPC and Subnets** isolate networks  
All this is typically managed via Terraform or Ansible.

---

### ✅ 6. How do you monitor EC2 instances?
**Answer:**  
- **CloudWatch** monitors CPU, memory, and disk  
- **CloudWatch Logs** or **Logstash** ship logs  
- Third-party tools like **Datadog**, **Zabbix**, or **Prometheus** provide more detailed monitoring

---

### ✅ 7. Differences: On-Demand vs Reserved vs Spot Instances?
**Answer:**  
- **On-Demand:** Pay per hour/second, flexible  
- **Reserved:** Commit for 1–3 years, cheaper  
- **Spot:** Cheapest, but can be interrupted  
DevOps teams often use Spot for CI agents to save costs.

---

### ✅ 8. How do Auto Scaling and ELB work with EC2?
**Answer:**  
Auto Scaling dynamically adds/removes EC2 instances based on load. Load Balancers distribute traffic. Together, they ensure uptime and responsiveness, especially for stateless microservices.

---

### ✅ 9. How do you manage EC2 costs?
**Answer:**
- Right-size instances  
- Use **Reserved** for steady workloads  
- Use **Spot Instances** for CI  
- Use **AWS Budgets**, **Auto Shutdown**, and **Monitoring Alarms**  

---

### ✅ 10. Share a real-world use of EC2 in DevOps.
**Answer:**  
“In a previous project, we used EC2 to host Jenkins. Instances were provisioned using Terraform, and Jenkins agents were set up on Spot Instances. This allowed us to scale builds automatically and save on cost while pushing code through a fully automated pipeline integrated with GitHub and CodeDeploy.”

---

## ✅ Summary: EC2 in DevOps

| Feature | Purpose |
|--------|---------|
| EC2 | Compute power to host apps, tools |
| AMI | OS + software snapshots |
| Security Group | Network-level protection |
| IAM | Role-based access |
| Auto Scaling | On-demand elasticity |
| CloudWatch | Monitoring & alerts |
| SSH + Key Pair | Secure instance login |
| Terraform / Ansible | Automation tools |

---

