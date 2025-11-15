

---

## 💻 **Technical Round — Extended Networking Questions & Answers**

---

### **1. What is CIDR in AWS networking?**

**Answer:**
CIDR (Classless Inter-Domain Routing) defines the range of IP addresses in your network.
Example: `10.0.0.0/16` gives **65,536 IP addresses**, while `10.0.1.0/24` gives **256 IPs**.
It helps efficiently allocate IPs in VPC and subnets.

---

### **2. What are Subnets and why do we create them?**

**Answer:**
Subnets divide a VPC into smaller networks.
They help organize resources — for example, **public subnets** for web servers and **private subnets** for databases.
Each subnet is tied to an Availability Zone (AZ).

---

### **3. What is a Route Table in AWS?**

**Answer:**
A Route Table defines where network traffic is directed.
For example:

* Local traffic (within the VPC) stays inside.
* Internet-bound traffic goes to the **Internet Gateway**.
* Private network traffic goes through a **NAT Gateway**.

---

### **4. What is an Internet Gateway (IGW)?**

**Answer:**
An IGW allows instances in public subnets to connect to the internet.
It’s attached to the VPC and routes traffic with a public IP.

---

### **5. What is a NAT Gateway and how is it different from IGW?**

**Answer:**

* **NAT Gateway:** Allows private subnet instances to access the internet **without exposing their IPs**.
* **Internet Gateway:** Allows **public subnet** instances to directly communicate with the internet.

---

### **6. What are Security Groups vs NACLs?**

**Answer:**

| Feature          | Security Group                       | NACL                       |
| ---------------- | ------------------------------------ | -------------------------- |
| Level            | Instance level                       | Subnet level               |
| Stateful         | Yes                                  | No                         |
| Rule Direction   | Inbound + Outbound                   | Inbound + Outbound         |
| Default Behavior | Deny all inbound, allow all outbound | Allow all inbound/outbound |

---

### **7. What is a Bastion Host and why is it used?**

**Answer:**
A Bastion Host (or Jump Server) provides **secure access** to instances in a private subnet through SSH.
It acts as a **gateway for administrators** to manage private resources.

---

### **8. What is AWS Direct Connect?**

**Answer:**
AWS Direct Connect provides a **dedicated network connection** from on-premise infrastructure to AWS.
It reduces latency and provides a more stable connection compared to the public internet.

---

### **9. What is VPC Peering?**

**Answer:**
VPC Peering connects two VPCs so that resources can communicate privately using private IPs.
It’s useful for connecting different teams, departments, or environments.

---

### **10. What is AWS Transit Gateway?**

**Answer:**
It acts as a **central hub** that connects multiple VPCs and on-prem networks.
Instead of creating multiple peering connections, you connect all VPCs to one Transit Gateway — simplifying management.

---

### **11. What is Elastic Load Balancer (ELB)?**

**Answer:**
ELB automatically distributes incoming traffic across multiple EC2 instances.
It improves **availability** and **fault tolerance**.
Types:

* Application Load Balancer (ALB)
* Network Load Balancer (NLB)
* Gateway Load Balancer (GLB)

---

### **12. What is CloudFront and how does it improve performance?**

**Answer:**
CloudFront is a **Content Delivery Network (CDN)** that caches data at edge locations globally.
It improves latency and speeds up website content delivery by serving users from the nearest AWS location.

---

### **13. What is DNS and how does Route 53 manage it?**

**Answer:**
DNS converts domain names into IP addresses.
**Route 53** provides:

* Domain registration
* DNS routing
* Health checks
* Traffic management using routing policies (Simple, Weighted, Latency-based, Geolocation)

---

### **14. What is the difference between Static IP, Public IP, and Elastic IP?**

**Answer:**

* **Static IP:** Doesn’t change (concept).
* **Public IP:** Assigned dynamically when launching instances.
* **Elastic IP:** Permanent static IP assigned to your AWS account that can be remapped to any instance.

---

### **15. What are PrivateLink and Endpoint Services in AWS?**

**Answer:**
PrivateLink allows you to securely access AWS services (like S3 or EC2 API) using private IPs inside your VPC — **without using public internet**.

---

### **16. What is VPC Flow Logs?**

**Answer:**
VPC Flow Logs capture IP traffic data (accepted/rejected) to and from network interfaces.
Used for **security analysis, troubleshooting, and compliance.**

---

### **17. What is the default VPC and can you delete it?**

**Answer:**
Each region has a **default VPC** with pre-configured subnets, route tables, and IGW.
You can delete it but usually better to create a **custom VPC** for better control and security.

---

### **18. How would you design a secure 3-tier architecture on AWS?**

**Answer:**

1. **Public Subnet:** Web servers behind an ALB
2. **Private Subnet:** Application servers
3. **Private Subnet:** Database (RDS)
4. Use Security Groups for traffic control, NAT Gateway for outbound internet, and IAM roles for access management.

---

### **19. How can you connect on-premise networks to AWS VPC?**

**Answer:**
Through:

* **VPN Connection** (Site-to-Site VPN)
* **AWS Direct Connect**
* **Transit Gateway** for multi-network connectivity

---

### **20. How do you troubleshoot connectivity issues in AWS networking?**

**Answer:**
Check:

1. **Security Groups & NACLs**
2. **Route Tables**
3. **Subnet association**
4. **DNS resolution**
5. **VPC Flow Logs**

