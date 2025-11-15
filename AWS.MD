

# 📘 AWS Trainer – 50 Interview Questions (with Answers)

Here are the **latest updates** on the AWS Free Tier / Free Account plan — good to know for interview/training.
I’ll break it into what’s *new*, what remains the same, and what to watch out for.

---

### 🆕 What’s New

* AWS now offers a **“Free Plan”** option for new accounts created on or after **July 15, 2025**. ([AWS Documentation][1])
* Under this new model:

  * You receive **USD $100 in credits** on sign-up. ([AWS Documentation][1])
  * You can *earn* **up to USD $100 more credits** by completing specific activities (e.g., launching an EC2 instance, creating a budget) — making up to USD $200 total. ([Amazon Web Services, Inc.][2])
* The Free Plan lasts **6 months**, or until the credits are used up—whichever comes first. ([AWS Documentation][1])
* Free Plan accounts **cannot** access some “expensive / enterprise grade” services until you upgrade to a paid plan. ([AWS Documentation][3])
* If you created your AWS account *before* July 15, 2025, you are under the “legacy” Free Tier model (12-month + always free). ([AWS Documentation][4])

---

### ✅ What Remains the Same / Always Free

* The “Always Free” services (with monthly usage limits) are still available—these apply to both old and new accounts. ([DEV Community][5])
* The Free Tier or Free Plan still allows you to **experiment and learn AWS at no cost**, provided you stay within limits.
* Standard sign-up steps (email, card, phone verification) remain required.

---

### ⚠️ What to Watch Out For

* Under the new Free Plan model, once the **6-month period ends** or your credits hit zero, if you *do not upgrade* to a paid plan → your account will **close**, and data will be deleted after a 90-day grace period. ([DEV Community][5])
* Some services may *not* be eligible under the Free Plan until you upgrade (e.g., certain Marketplace purchases, dedicated hardware infrastructure). ([AWS Documentation][3])
* Being under the legacy Free Tier (12-month model) means you continue with that older model if you created the account before the cutoff. New accounts won’t get the same 12-month unlimited like before.
* Always monitor usage carefully: using services beyond limits may consume credits or incur charges if upgraded to paid plan.

---

### 🎯 Quick Summary For Interview Use

* New accounts (after July 15, 2025) = Free Plan: **$100 credits** on sign-up + up to **$100 extra** possible → **$200** total.
* Duration: **6 months** max for Free Plan. After that, upgrade to keep account.
* Legacy model (pre-July 15, 2025) = 12-month Free Tier + always free services.
* Always-Free services remain available indefinitely (within limits).
* Upgrade to Paid Plan when doing production workloads or using services not covered by Free Plan.

---

If you like, I can **pull the official AWS Free Tier changes into a printable cheat sheet (PDF)** with exact service limits and dates. Would that be helpful?

[1]: https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier.html?utm_source=chatgpt.com "Explore AWS services with AWS Free Tier - AWS Billing"
[2]: https://aws.amazon.com/blogs/aws/aws-free-tier-update-new-customers-can-get-started-and-explore-aws-with-up-to-200-in-credits/?utm_source=chatgpt.com "AWS Free Tier update: New customers can get started and ..."
[3]: https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-plans.html?utm_source=chatgpt.com "Choosing an AWS Free Tier plan - AWS Billing"
[4]: https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-free-tier.html?utm_source=chatgpt.com "Trying services using AWS Free Tier (before July 15, 2025)"
[5]: https://dev.to/aws-builders/whats-new-in-aws-free-tier-2025-2ba5?utm_source=chatgpt.com "What's New in AWS Free Tier (2025)"


## ## 🧩 **Section 1: HR & Training Methodology (10 Questions)**

### **1. Tell me about your experience as an AWS Trainer.**

I have worked as an AWS Trainer for *X* years, delivering hands-on training on core AWS services like EC2, IAM, S3, VPC, and advanced services based on the learner level. I also prepare learning materials, labs, and mock tests.

### **2. How do you handle mixed-skill classrooms?**

By using differentiated instruction—parallel tasks, extra practice for slow learners, and advanced labs for fast learners.

### **3. What makes you a good trainer?**

Clear communication, real-world examples, patience, and strong cloud expertise.

### **4. How do you make classes interactive?**

Live demos, quizzes, scenario discussions, whiteboard diagrams, and debugging exercises.

### **5. What is your content creation process?**

I follow: Topic → Simplify → Create diagrams → Add use cases → Build hands-on lab.

### **6. How do you track student progress?**

Daily quizzes, hands-on lab outcomes, weekly evaluations, and Q&A sessions.

### **7. How do you simplify complex AWS topics?**

By using real-life analogies, step-by-step diagrams, and small labs.

### **8. How do you prepare students for certifications?**

Topic explanation → Demo → Lab → Reinforcement notes → Mocks → Exam strategy.

### **9. How do you handle student doubts after sessions?**

Dedicated doubt-clearing sessions, WhatsApp groups, and recorded content access.

### **10. What tools do you use for training delivery?**

Zoom/Meet, Whiteboard, AWS Console, CLI, GitHub, Notion/Docs for notes.

---

## ## ☁️ **Section 2: AWS Core Services (10 Questions)**

### **11. What is EC2?**

Elastic Compute Cloud – virtual servers with scalable compute resources.

### **12. What is the difference between AMI and Snapshot?**

AMI: Complete image for launching instances.
Snapshot: Backup of EBS volume.

### **13. What is S3 versioning?**

A feature to keep multiple versions of an object, useful for backup & rollback.

### **14. What is IAM Role vs User?**

User = long-term identity for humans.
Role = temporary credentials for AWS services.

### **15. What is the difference between EBS and Instance Store?**

EBS = persistent
Instance Store = temporary storage

### **16. What is Load Balancer?**

Distributes traffic across multiple EC2 instances for high availability.

### **17. Explain Auto Scaling.**

Automatically adds/removes EC2 instances based on load.

### **18. What is CloudWatch?**

Monitoring service for logs, metrics, alarms, dashboards.

### **19. What is CloudTrail?**

Tracks API calls for auditing and compliance.

### **20. How do you host a static website?**

Using S3 Static Website Hosting + Public Access + Optional CloudFront.

---

## ## 🌐 **Section 3: AWS Networking (10 Questions)**

### **21. What is a VPC?**

Virtual Private Cloud — your own private AWS network.

### **22. What are public and private subnets?**

Public → IGW attached
Private → NAT Gateway for outgoing traffic

### **23. What is a Route Table?**

Defines routes for subnet traffic.

### **24. What is CIDR?**

IP addressing format like 10.0.0.0/16.

### **25. Difference: Security Groups vs NACLs**

SG: Stateful (instance level)
NACL: Stateless (subnet level)

### **26. What is NAT Gateway?**

Allows private subnet instances to access the internet securely.

### **27. What is VPC Peering?**

Private connection between two VPCs.

### **28. What is an Internet Gateway?**

Allows communication between VPC resources and the internet.

### **29. What is a Bastion Host?**

Secure jump server to access private EC2 instances.

### **30. What are VPC Endpoints?**

Private access to AWS services without internet.

---

## ## 🗄️ **Section 4: Storage & Database (5 Questions)**

### **31. What is EFS?**

Elastic File System — scalable shared storage.

### **32. What is RDS?**

Managed relational database service.

### **33. RDS Multi-AZ vs Read Replica?**

Multi-AZ = HA
Read Replica = Read scaling

### **34. What is DynamoDB?**

Fully managed NoSQL database with low-latency access.

### **35. What is Glacier?**

Low-cost archival storage for long-term data backup.

---

## ## 🔐 **Section 5: Security & IAM (5 Questions)**

### **36. What is MFA?**

Multi-Factor Authentication adds extra layer of security.

### **37. What is KMS?**

Key Management Service for encryption keys.

### **38. What is SCP in AWS Organizations?**

Service Control Policies that restrict permissions across accounts.

### **39. Principle of Least Privilege?**

Give users only the minimum required access.

### **40. What are Resource Policies?**

Policies attached directly to AWS resources (e.g., S3 bucket policy).

---

## ## ⚙️ **Section 6: DevOps, CLI & Automation (5 Questions)**

### **41. What is AWS CLI?**

Command-line tool to manage AWS resources programmatically.

### **42. What is CloudFormation?**

Infrastructure-as-code to deploy AWS resources.

### **43. What is CodePipeline?**

CI/CD pipeline automation service.

### **44. What is CodeBuild?**

Build service for compiling, testing, and packaging code.

### **45. What is Elastic Beanstalk?**

PaaS for deploying applications easily without infrastructure management.

---

## ## 🛠️ **Section 7: Real-Life AWS Scenarios (5 Questions)**

### **46. Your student is unable to SSH into EC2. What do you check?**

Key pair → SG inbound rules → Private IP → Correct username → IAM permissions → Running instance state.

### **47. Website is slow. What AWS services can improve performance?**

CloudFront, ALB, Auto Scaling, ElastiCache.

### **48. How do you reduce S3 storage cost?**

Lifecycle rules, Intelligent-Tiering, delete unused versions.

### **49. How do you secure a training AWS account?**

MFA, IAM roles, billing alarms, CloudTrail, least privilege.

### **50. A student accidentally deleted an EC2 instance. What is your recovery approach?**

Restore from EBS snapshot or AMI.


