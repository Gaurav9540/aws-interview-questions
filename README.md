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
 VPC (10.0.0.0/16)
 │
 ├── Public Subnet (10.0.1.0/24) - Web Servers (With Internet Gateway)
 │
 ├── Private Subnet (10.0.2.0/24) - Application Servers (No Internet Access)
 │
 └── Private Subnet (10.0.3.0/24) - Databases (RDS) (Completely Private)



