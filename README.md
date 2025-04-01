# aws-interview

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

**10. What is CloudFront ?** <br>
AWS CloudFront is a Content Delivery Network (CDN) service that accelerates the delivery of websites, APIs, videos, and other web assets by caching content closer to users at AWS Edge Locations worldwide. <br>
CloudFront Architecture: <br>
User Request → Edge Location (Cache) → (If Cache Miss) → Origin Server (S3, EC2, ALB) <br>

<hr>

**11. What is CloudWatch ?** <br>
AWS CloudWatch is a monitoring and observability service that collects and analyzes logs, metrics, and events from AWS resources and applications. It helps you track performance, detect anomalies, set alerts, and automate responses to system changes. <br>
AWS CloudWatch is an essential tool for real-time monitoring, logging, and automation in AWS environments. <br>

<hr>

**12. What is LAMDA Service in AWS ?** <br>
AWS Lambda is a serverless compute service that allows you to run code without provisioning or managing servers. You only pay for the compute time you consume. Lambda automatically manages the underlying infrastructure, so you can focus purely on writing and deploying your code. <br>

<hr>

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
```

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

**18. Absolute Path v/s Relative Path ?** <br>
1. Absolute Path <br>
   The full path to a file or directory from the root (/) directory. <br>
   Always starts with a /. <br>
   Works from any location in the system. <br>

2. Relative Path <br>
   A path relative to the current working directory. <br>
   Does not start with /. <br>
   Depends on where you are in the system. <br>

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

**22. OSI model (Open Systems Interconnection Model)** <br>
The OSI model is a 7-layer conceptual framework that describes how data moves through a network. Each layer has a specific function and interacts with the layers above and below it. <br>

<img src="Screenshot 2025-04-01 233037.png" alt="Project Screenshot" width="800">


<hr>

**GitHub** <br>

4 basic commands of git: <br>

```ssh
git init
git add .
git commit -M "commit message"
git remote add origin "link"
git pull --rebase
git push origin main
```

rebase --> Fetches the latest changes from the remote repository



