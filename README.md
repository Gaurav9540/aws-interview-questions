# aws-interview

**Introduction** <br>
  Name <br>
  Location <br>
  Education <br>
  Skills <br>
  Family Background <br>
  Hobbies <br>
  Short Term and Long Term Goal <br>


**1. What is IAM Service and How Enhance Security ?** <br>
AWS IAM (Identity and Access Management) is a service that helps manage user access and permissions securely across AWS resources. It allows you to control who can access what in AWS. <br>
How IAM Enhances Security <br>
1. Least Privilege Access <br>
2. Multi-Factor Authentication (MFA) <br>
3. IAM Roles for Services <br>
4. Use IAM Groups <br>

<hr>

**2. What is EC2 ?** <br>
Amazon EC2 (Elastic Compute Cloud) is a web service that provides resizable computing capacity in the cloud. It allows users to run virtual servers (instances) on demand, eliminating the need to invest in physical hardware.

**Instance Types :** <br>
1️⃣ General Purpose <br>
2️⃣ Compute Optimized <br>
3️⃣ Memory Optimized <br>
4️⃣ Storage Optimized <br>
5️⃣ Accelerated Computing <br>
6️⃣ HPC Optimized <br>

**EC2 Purchasing Models :** <br>
1️⃣ On-Demand Instances (Pay-as-You-Go) <br>
2️⃣ Reserved Instances (RIs) <br>
3️⃣ Savings Plans (Flexible Cost Savings) <br>
4️⃣ Spot Instances (Up to 90% Discount!) <br>
5️⃣ Dedicated Hosts (Physical Server for You Only) <br>
6️⃣ Dedicated Instances (Private EC2 Instances)  <br>
7️⃣ Capacity Reservations <br>

<hr>

**3. What is Horizontal Scalling & Vertical Scalling ?** <br>
Auto Scaling in AWS helps dynamically adjust computing resources to meet application demands. There are two main types of scaling: Horizontal Scaling and Vertical Scaling. <br>

1. Horizontal Scaling (Scaling Out/In) - 
Definition: Horizontal scaling (also called scaling out) involves adding more EC2 instances to distribute the workload. Scaling in removes instances when demand decreases.

2. Vertical Scaling (Scaling Up/Down) - 
Definition: Vertical scaling (also called scaling up) involves increasing the size (CPU, RAM, disk) of a single EC2 instance. Scaling down reduces the instance size when demand decreases.


**4. Steps to Create Auto Scalling in AWS ?** <br>
Auto Scaling in AWS ensures that your application can handle varying levels of traffic by automatically adding or removing EC2 instances. Follow these steps to set up Auto Scaling in AWS: <br>
Step 1: Create a Launch Template or Launch Configuration <br>
Step 2: Create an Auto Scaling Group <br>
Step 3: Configure Scaling Policies <br>
Step 4: Attach a Load Balancer (Optional) <br>
Step 5: Review and Create <br>

<hr>

**5. ALB (Application Load Balancer) v/s ASG (Auto Scaling Group) ?** <br>
ALB (Application Load Balancer) and ASG (Auto Scaling Group) are both AWS services that improve availability, scalability, and reliability, but they serve different purposes. <br>
1. What is ALB (Application Load Balancer)? <br>
✅ Purpose: ALB distributes incoming traffic across multiple EC2 instances in different availability zones to ensure load balancing. <br>

2. What is ASG (Auto Scaling Group)? <br>
✅ Purpose: ASG automatically scales EC2 instances up or down based on demand. <br>


 **6. What is Load Balancing ?** <br>
 Load balancing is the process of distributing incoming network traffic evenly across multiple servers or resources to ensure high availability, reliability, and 
 performance. <br>
 In AWS, Elastic Load Balancing (ELB) automatically distributes traffic across EC2 instances, containers, and even Lambda functions. <br>

 Types of Load Balancers in AWS <br>
 1. Classic Load Balancer (CLB) <br>
 2. Application Load Balancer (ALB) <br>
 3. Network Load Balancer (NLB) <br>
 4. Gateway Load Balancer (GLB) <br>

 <hr>

 **7. What is VPC ?** <br>
 AWS VPC (Virtual Private Cloud) is a private, isolated network within AWS that allows you to securely run cloud resources like EC2, RDS, and Lambda. <br>
 Think of it as your own data center in the cloud, where you can define networking rules, control access, and connect to the internet or other networks. <br>

 **8. Components of VPC ?** <br>
 1. CIDR Block (IP Address Range) <br>
 2. Subnets (Public & Private) <br>
 3. Internet Gateway (IGW) <br>
 4. NAT Gateway <br>
 5. Route Tables <br>
 6. Security Groups & NACLs <br>

 VPC Architecture Example: <br>
 VPC (10.0.0.0/16) <br>
 │ <br>
 ├── Public Subnet (10.0.1.0/24) - Web Servers (With Internet Gateway) <br>
 │ <br>
 ├── Private Subnet (10.0.2.0/24) - Application Servers (No Internet Access) <br>
 │ <br>
 └── Private Subnet (10.0.3.0/24) - Databases (RDS) (Completely Private) <br>


**9. Private Subnet v/s Public Subnet ?** <br>
1. Public Subnet - 
A public subnet has direct internet access because it is associated with an Internet Gateway (IGW) and has a route to 0.0.0.0/0. <br>

2. Private Subnet -
A private subnet has no direct internet access—it does NOT have a route to an Internet Gateway (IGW). <br>

Public vs. Private Subnet Architecture Example <br>
VPC (10.0.0.0/16) <br>
│ <br>
├── Public Subnet (10.0.1.0/24) - Web Servers, ALB  [Connected to IGW] <br>
│ <br>
├── Private Subnet (10.0.2.0/24) - App Servers [No Internet Access] <br>
│ <br>
└── Private Subnet (10.0.3.0/24) - Database (RDS) [Completely Private] <br>

<hr>

 **Diff Between Security groups and NACL**
 
 1. Security Groups - A Security Group in AWS acts as a virtual firewall that controls the inbound and outbound traffic to your AWS resources, such as EC2 instances, RDS databases, etc.
     - stateful only define inbound rule outbound rule managed by aws
     - we can create security group at instance level
     - we can add only allow rule deny rule not possible in security group 
        
2. NACL - A Network ACL (NACL) in AWS is a network-level firewall that controls traffic in and out of subnets in your VPC (Virtual Private Cloud).
     - stateless need to efine both inbound as well as outbound rules
     - we can create NACL at subnet level
     - we can add allow as well as deny rule in NACL
     - mostly use in complex scenarios

  - if we create an NACL all the Inbound and Outbound rules are by default deny
  - but the by default NACL all the Inbound and Outbound rules are by default allow

<hr>

**10. What is CloudFront ?** <br>
AWS CloudFront is a Content Delivery Network (CDN) service that accelerates the delivery of websites, APIs, videos, and other web assets by caching content closer to users at AWS Edge Locations worldwide. <br>
CloudFront Architecture: <br>
User Request → Edge Location (Cache) → (If Cache Miss) → Origin Server (S3, EC2, ALB) <br>

<hr>

**11. What is CloudWatch ?** <br>
AWS CloudWatch is a monitoring and observability service that collects and analyzes logs, metrics, and events from AWS resources and applications. It helps you track performance, detect anomalies, set alerts, and automate responses to system changes. <br>
AWS CloudWatch is an essential tool for real-time monitoring, logging, and automation in AWS environments. <br>

<hr>

**What is Route53 ?** <br>
Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service provided by AWS.  <br>
It is used for domain registration, DNS management, and traffic routing across AWS and external resources. <br>

<hr>

**What is RDS ?** <br>
Amazon RDS (Relational Database Service) is a managed database service provided by AWS that makes it easy to set up, operate, and scale relational databases in the cloud.  <br>
It automates tasks like provisioning, backups, patching, and scaling. <br>

<hr>

**What is SQS ?** <br>
Amazon SQS (Simple Queue Service) is a fully managed message queuing service offered by AWS. <br>
It enables decoupling of components in a distributed application so they can communicate reliably and asynchronously. <br>

🔧 Key Concepts: <br>
Queue: A buffer that temporarily stores messages. <br>
Producers: Send messages to the queue. <br>
Consumers: Retrieve and process messages from the queue. <br>

<hr>

**What is SNS ?** <br>
Amazon SNS (Simple Notification Service) is a fully managed pub/sub messaging and mobile notification service in AWS.  <br>
It allows applications, services, or users to send messages to multiple subscribers instantly. <br>

📦 Use Cases: <br>
Application alerts & monitoring <br>
Mobile push notifications (iOS, Android) <br>
Sending messages from one app to another via Lambda/SQS <br>

ex: A CloudWatch alarm triggers when CPU usage is too high. <br>
<hr>

**What is SES ?** <br>
Amazon SES (Simple Email Service) is a cloud-based email sending service provided by AWS. <br>
It's used to send and receive emails at scale, securely and cost-effectively. <br>

📧 What SES Does: <br>
Send transactional emails (e.g., order confirmations, password resets) <br>
Send marketing/bulk emails (e.g., newsletters) <br>
Receive and process incoming emails <br>
Monitor email delivery, open rates, bounces, complaints <br>

<hr>

**12. What is LAMDA Service in AWS ?** <br>
AWS Lambda is a serverless compute service provided by Amazon Web Services. <br>
It lets you run code without provisioning or managing servers. <br>
⚡ In Simple Terms: <br>
Lambda lets you write a function (code) and run it only when it's needed, and you only pay for the compute time you use. No need to manage servers! <br>
<br>
⚙️ Common Use Cases: <br>
🔁 Running background tasks (e.g., image processing) <br>
🌐 Building APIs (with API Gateway + Lambda) <br>
📁 Reacting to S3 events (e.g., when a file is uploaded) <br>
🧠 Automating cloud resource management <br>
<br>
🧪 Example: <br>
Imagine someone uploads a photo to an S3 bucket. You can use a Lambda function to automatically resize the image or create a thumbnail. <br>
<hr>

**12.1 Diff Between AMI, Launch Template and Snaphot** <br>

 **AMI (Amazon Machine Image) -** <br>
   An AMI is a pre-configured image that contains the OS, application, and necessary settings to launch EC2 instances. <br>
   It includes system disk snapshots and metadata like permissions and block device mappings. <br>
   AMIs can be customized, shared across AWS accounts, and used for scaling. <br> 
   **Use case:** Creating identical EC2 instances with the same OS, software, and configurations. <br>
 
 **EC2 Launch Template -** <br>
   A Launch Template is a blueprint that defines instance configurations such as AMI, instance type, security groups, key pairs, storage, and IAM roles. <br>
   It helps streamline instance creation without manually setting configurations each time. <br>
   Supports versioning, allowing you to update configurations while maintaining previous versions. <br>
   **Use case:** Automating instance launches using Auto Scaling Groups (ASG) and EC2 Fleet. <br>

  **Snapshot -** <br>
   A Snapshot is a backup of an EBS volume (Elastic Block Store), capturing its state at a specific point in time. <br>
   Snapshots are incremental (only storing changes after the first full snapshot). <br>
   They can be used to create new volumes or AMIs. <br>
   **Use case:** Disaster recovery, data backup, and migrating data between AWS regions. <br>

**LINUX** <br>

**13. /etc/passwd fields -**  
The /etc/passwd file in Linux stores user account information. <br>
Fields in /etc/passwd File : <br>

```ssh
username:password:UID:GID:comment:home_directory:shell
```

**14. /etc/shadow fields -** <br>
The /etc/shadow file in Linux stores password information in a secure format for system authentication. <br>
Fields in /etc/shadow File : <br>

```ssh
username:password:last_change:min:max:warn:inactive:expire:reserved
```

<hr>

**15. What is Crontab ?** <br>
Crontab (Cron Table) is a Linux utility used to schedule automated tasks (cron jobs) at specified intervals. It is part of the cron daemon, which runs background tasks at predetermined times. <br>

Why Use Crontab? <br>
✅ Automates repetitive tasks (backups, updates, scripts) <br>
✅ Runs tasks hourly, daily, weekly, or custom intervals <br>
✅ Saves time and reduces human errors <br>

```ssh
crontab -e   ---> to edit crontab
crontab -l   ---> to view cron jobs
crontab -r   ---> to remove cron job
```
crontab fields:  <br>

```ssh
MIN  HOUR  DOM  MON  DOW  COMMAND
ex. 0 2 * * *  command ---> runs everyday at 2PM
```

<hr>

**16. How to Change Ownership in Linux ?** <br>
In Linux, the chown (change owner) command is used to change the ownership of files and directories. You can change both the owner and group of a file. <br>

syntax - chown [OPTIONS] NEW_OWNER:NEW_GROUP FILE  <br>

NEW_OWNER → The new owner (username). <br>
NEW_GROUP → (Optional) The new group. <br>
FILE → The file or directory to modify. <br>

1. Change File Owner --> chown user1 file.txt  <br>
   🔹 Example: Change ownership of file.txt to john  <br>
       chown john file.txt <br>

2. Change Owner and Group --> chown user1:group1 file.txt <br>
   🔹 Example: Change owner to john and group to developers <br>
       chown john:developers file.txt <br>

3. Change Ownership for a Directory (Recursively) --> chown -R user1:group1 /path/to/directory <br>
   🔹 Example: Change ownership of /var/www/html to www-data <br>
       chown -R www-data:www-data /var/www/html <br>

4. Check File Ownership ---> ls -l file.txt <br>


**17. How to Change File Permission ?** <br>
File permissions in Linux control who can read, write, or execute files and directories. You can modify them using the chmod command. <br>

syntax: <br>
```ssh
chmod 750 file.txt

7 → Owner (rwx = 4+2+1 = 7)
5 → Group (r-x = 4+0+1 = 5)
0 → Others (no permissions)

       OR

chmod u+rwx,g+rx,o-r file.txt
```

<hr>

**18. Absolute Path v/s Relative Path ?** <br>
1. Absolute Path <br>
   The full path to a file or directory from the root (/) directory. <br>
   Always starts with a /. <br>
   Works from any location in the system. <br>

2. Relative Path <br>
   A path relative to the current working directory. <br>
   Does not start with /. <br>
   Depends on where you are in the system. <br>

<hr>

**19. used of ping -**
The ping command is used to test network connectivity between two devices. <br>
destination can be an IP address or a domain name (e.g., ping google.com). <br>

**20. traceroute -** 
The traceroute command is used to trace the path that network packets take to reach a destination. It helps in diagnosing network issues by displaying each router (or hop) along the way and the time it takes to reach them. <br>

```ssh
1. Basic Syntax - traceroute [options] destination
2. Example Usage - traceroute google.com
```

**21. tcpdump -**
tcpdump is a powerful packet sniffer tool used to capture and analyze network traffic in Linux. It works by capturing packets on a specified interface and displaying them in real time. <br>

```ssh
1. Basic Syntax - tcpdump [options] [expression]
   Options: Modify the capture behavior.
   Expression: Filter packets based on protocols, ports, IPs, etc.
```

<hr>

**22. OSI model (Open Systems Interconnection Model)** <br>
The OSI model is a 7-layer conceptual framework that describes how data moves through a network. Each layer has a specific function and interacts with the layers above and below it. <br>

<img src="Screenshot 2025-04-01 233037.png" alt="Project Screenshot" width="800">


<hr>

**GitHub** <br>

**Git** <br>
A distributed version control system used for tracking code changes. <br>
Helps in collaboration and managing different versions of the codebase. <br>

**GitHub** <br>
A cloud-based platform for hosting Git repositories. <br>
Provides features like pull requests, issue tracking, and CI/CD integrations. <br>

4 basic commands of git: <br>

```ssh
git init
git add .
git commit -M "commit message"
git remote add origin "link"
git pull --rebase
git push origin main
```
rebase --> Fetches the latest changes from the remote repository <br>


<hr>


**Fail2Ban -**
An intrusion prevention tool that detects and bans IP addresses with suspicious activity. <br>
Protects against brute-force attacks on SSH and other services. <br>

**Auditd -**
A Linux auditing tool that tracks system activity, user logins, and file changes.  <br>
Helps with compliance and security monitoring. <br>








