# 📚 Complete Structured Study Plan
## Infrastructure Specialist - Cloud Platform (AWS & Azure)
### All 31 Modules - Complete Reference Guide
---
## 🗓️ Master Overview
| Parameter | Details |
|-----------|---------|
| **Total Training Duration** | 6 Weeks Training + 2 Weeks Induction + 3 Weeks Shadow |
| **Total Days** | 30 Days |
| **Target Certifications** | AWS SOA-C02 + AZ-104 |
| **Recommended Certifications** | AWS Cloud Architect Associate, AWS Developer, AWS DevOps Engineer |
| **Sandbox Credits** | $10 on AWS, Azure & Google |
---
## 📅 Weekly Structure at a Glance
| Week | Focus Area | Modules |
|------|-----------|---------|
| Week 1-2 | Foundation & Core Infrastructure | Modules 1-6 |
| Week 3 | AWS Core Services | Modules 7-11 |
| Week 4 | AWS Advanced Services | Modules 12-16 |
| Week 5 | Azure Administration | Modules 17-24 |
| Week 6 | Azure Advanced + DevOps + MicroServices | Modules 25-31 |
---
# 🟦 WEEKS 1-2: FOUNDATION & CORE INFRASTRUCTURE
---
## 📦 MODULE 1: Linux Fundamentals
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 1.1 Introduction to Linux
- What is Linux?
- Linux Distributions and Flavors
  - Ubuntu
  - CentOS/RHEL
  - Debian
  - Amazon Linux
- Different Ways to Access Linux Servers
  - SSH (Secure Shell)
  - Console Access
  - Remote Desktop (VNC/RDP)
### 1.2 File System Operations
- Working with Directories
  - pwd, ls, cd, mkdir, rmdir
  - Absolute vs Relative Paths
- Working with Files
  - touch, cat, cp, mv, rm
  - vi/nano editors
  - File Permissions (chmod, chown)
### 1.3 Basic Linux Commands
- System Commands (uname, hostname, uptime)
- Process Management (ps, top, kill)
- Package Management (apt/yum/rpm)
- Text Processing (grep, awk, sed)
- Piping and Redirection
### 1.4 User and Group Management
- Creating Users (useradd, adduser)
- Modifying Users (usermod)
- Deleting Users (userdel)
- Group Management (groupadd, groupmod)
- Password Management (passwd)
- /etc/passwd and /etc/shadow files
### 1.5 File System on Linux
- Linux File System Hierarchy
  - / (Root)
  - /home
  - /etc
  - /var
  - /tmp
- Mounting and Unmounting
- Disk Management (df, du, fdisk)
- LVM (Logical Volume Manager) Basics
### 1.6 Networking on Linux
- ifconfig / ip commands
- netstat, ss commands
- ping, traceroute, nslookup
- /etc/hosts, /etc/resolv.conf
- Firewall basics (iptables/firewalld)
### 1.7 Troubleshooting Basics
- Log files (/var/log/)
- System journal (journalctl)
- Common error diagnosis
- Service management (systemctl)
### 📖 Resources
- [Complete Linux Training Course - Udemy (IBM Learning)](https://ibm-learning.udemy.com/course/complete-linux-training-course-to-get-your-dream-it-job/)
- [RHEL - YourLearning](https://yourlearning.ibm.com/activity/SMT-3862)
### ✅ Hands-On Practice Goals
- [ ] Navigate entire Linux file system
- [ ] Create/modify/delete users and groups
- [ ] Set file permissions using chmod
- [ ] Manage processes using ps and kill
- [ ] Configure basic network settings
- [ ] Read and analyze log files
---
## 📦 MODULE 2: Cloud Overview & Concepts
> **Duration:** 1 Day | **Format:** Lecture
### 2.1 What is Cloud Computing?
- Definition and Key Characteristics
- On-demand Self Service
- Broad Network Access
- Resource Pooling
- Rapid Elasticity
- Measured Service
### 2.2 Types of Cloud Services
- **IaaS (Infrastructure as a Service)**
  - Definition
  - Examples: AWS EC2, Azure VM
  - Use Cases
- **PaaS (Platform as a Service)**
  - Definition
  - Examples: AWS Elastic Beanstalk, Azure App Service
  - Use Cases
- **SaaS (Software as a Service)**
  - Definition
  - Examples: Gmail, Salesforce, Office 365
  - Use Cases
- **XaaS (Everything as a Service)**
  - Definition
  - Examples
### 2.3 Cloud Deployment Models
- **Public Cloud**
  - Definition
  - Pros and Cons
  - Examples: AWS, Azure, GCP
- **Private Cloud**
  - Definition
  - Pros and Cons
  - Use Cases
- **Hybrid Cloud**
  - Definition
  - Pros and Cons
  - Use Cases
- **Community Cloud**
  - Definition
  - Use Cases
### 2.4 Virtualization Concepts
- What is Virtualization?
- Types of Virtualization
  - Hardware/Server Virtualization
  - Network Virtualization
  - Storage Virtualization
- Hypervisors
  - Type 1 (Bare Metal)
  - Type 2 (Hosted)
- Virtual Machines Overview
### ✅ Study Goals
- [ ] Differentiate IaaS vs PaaS vs SaaS with real examples
- [ ] Compare Public vs Private vs Hybrid Cloud
- [ ] Explain virtualization and hypervisors
---
## 📦 MODULE 3: Networking Fundamentals
> **Duration:** 1 Day | **Format:** Lecture
### 3.1 Basic Networking Knowledge
- What is a Network?
- Network Topologies (Star, Bus, Ring, Mesh)
- LAN, WAN, MAN
- Network Devices (Router, Switch, Hub)
### 3.2 OSI Model (7 Layers)
| Layer | Name | Examples |
|-------|------|---------|
| Layer 1 | Physical | Cables, Hubs, Repeaters |
| Layer 2 | Data Link | MAC Address, Switches, Frames |
| Layer 3 | Network | IP Address, Routers, Packets |
| Layer 4 | Transport | TCP, UDP, Segments |
| Layer 5 | Session | Session Establishment/Termination |
| Layer 6 | Presentation | Encryption, Encoding, Compression |
| Layer 7 | Application | HTTP, FTP, DNS, SMTP |
### 3.3 IP Addressing
- IPv4 vs IPv6
- IP Address Classes
  - Class A (1.0.0.0 - 126.255.255.255)
  - Class B (128.0.0.0 - 191.255.255.255)
  - Class C (192.0.0.0 - 223.255.255.255)
  - Class D (Multicast)
  - Class E (Reserved)
- Subnetting
  - Subnet Masks
  - CIDR Notation
  - Calculating Subnets
- Public vs Private IP Addresses
- Assigning IP Addresses
  - Static Assignment
  - Dynamic Assignment (DHCP)
### 3.4 Routing
- Defining Routes
- Routing Tables
- Default Gateway
- Static vs Dynamic Routes
### 3.5 Hostname Configuration
- Setting Hostname
- FQDN (Fully Qualified Domain Name)
- /etc/hostname file
### 3.6 Name Resolution
- DNS Basics
- How DNS Works
- DNS Record Types
  - A Record
  - CNAME Record
  - MX Record
  - PTR Record
- /etc/hosts file
### ✅ Hands-On Practice Goals
- [ ] Identify all 7 OSI layers and their functions
- [ ] Calculate subnets using CIDR notation
- [ ] Configure static IP address on Linux
- [ ] Set hostname and configure name resolution
- [ ] Read and modify routing tables
---
## 📦 MODULE 4: Firewall, Load Balancer, Routing & Proxy
> **Duration:** 2 Days | **Format:** Lecture + Hands-On
### SECTION A: Firewall
#### 4.1 Basic Concepts of Firewall
- What is a Firewall?
- How Firewalls Work
- Types of Firewalls
  - Packet Filtering
  - Stateful Inspection
  - Application Layer
  - Next Generation Firewall (NGFW)
- Firewall Rules and Policies
#### 4.2 VPN (Virtual Private Network)
- Point-to-Point VPN Tunnels
  - Setup and Configuration
  - Use Cases
- Site-to-Site VPN Tunnels
  - Setup and Configuration
  - Use Cases
#### 4.3 IPS (Intrusion Prevention System)
- What is IPS?
- How IPS Works
- IPS vs Firewall
#### 4.4 IDS (Intrusion Detection System)
- What is IDS?
- How IDS Works
- IDS vs IPS Comparison
#### 4.5 Cloud Firewall
- Cloud Firewall Concepts
- Cloud Firewall Terminologies
- AWS Security Groups
- AWS Network ACLs
- Azure Network Security Groups
### SECTION B: Load Balancer
#### 4.6 Basic Load Balancer Concepts
- What is a Load Balancer?
- Why Load Balancing?
- Load Balancing Algorithms
  - Round Robin
  - Least Connections
  - IP Hash
  - Weighted Round Robin
- Health Checks
#### 4.7 Application Load Balancer (ALB)
- Basic Concepts
- Layer 7 Load Balancing
- Path-based Routing
- Host-based Routing
- Configuration Steps
#### 4.8 Network Load Balancer (NLB)
- Basic Concepts
- Layer 4 Load Balancing
- TCP/UDP Load Balancing
- Configuration Steps
#### 4.9 Placement of Load Balancers
- Public-facing Load Balancers
- Internal Load Balancers
#### 4.10 Certificates
- SSL/TLS Certificates
- Creating Certificates
- Attaching Certificates to Load Balancers
#### 4.11 Firewall Rules
- Application Firewall Rules
- Network Firewall Rules
### SECTION C: Routing
#### 4.12 Routing Protocols Overview
- Interior Gateway Protocols (IGP)
- Exterior Gateway Protocols (EGP)
#### 4.13 BGP (Border Gateway Protocol)
- BGP Overview
- BGP Peering
  - iBGP (Internal BGP)
  - eBGP (External BGP)
- BGP Attributes
#### 4.14 Static Routing
- What is Static Routing?
- When to Use Static Routing
- Configuration of Static Routes
#### 4.15 Dynamic Routing
- What is Dynamic Routing?
- OSPF Overview
- EIGRP Overview
- RIP Overview
#### 4.16 Router Configuration
- Basic Router Setup
- Interface Configuration
- Routing Table Management
### SECTION D: Proxy
#### 4.17 Proxy Concepts
- What is a Proxy?
- Types of Proxies
- Why Use a Proxy?
#### 4.18 Forward Proxy
- How Forward Proxy Works
- Use Cases
#### 4.19 Reverse Proxy
- How Reverse Proxy Works
- Use Cases
#### 4.20 Nginx as Proxy
- Installing Nginx
- Configuring Nginx as Forward Proxy
- Configuring Nginx as Reverse Proxy
- SSL Termination with Nginx
### 🔖 Case Studies
#### Case Study 1: Multi-tier Web Application Networking
- Placement of ALB for web tier
- Placement of NLB for application tier
- Firewall rules between tiers
- VPN tunnel for on-premises connectivity
- Proxy configuration for outbound traffic
#### Case Study 2: Secure Enterprise Network Design
- BGP peering configuration
- Site-to-Site VPN setup
- IDS/IPS placement
- Load balancer with SSL termination
- Reverse proxy with Nginx
### ✅ Hands-On Practice Goals
- [ ] Configure basic firewall rules
- [ ] Set up a Site-to-Site VPN tunnel
- [ ] Configure Application Load Balancer
- [ ] Configure Network Load Balancer
- [ ] Set up Nginx as reverse proxy
- [ ] Complete 2 case studies on network component placement
- [ ] Configure BGP peering
- [ ] Implement static and dynamic routing
- [ ] Attach SSL certificates to load balancer
---
## 📦 MODULE 5: Containers & Kubernetes
> **Duration:** 3 Days | **Format:** Lecture + Hands-On
### SECTION A: Container Fundamentals
#### 5.1 What is a Container?
- Definition
- Benefits of Containers
#### 5.2 VMs vs Containers
- Architecture Differences
- Resource Utilization
- Startup Time
- Portability
- Use Cases for Each
#### 5.3 Containerization Technologies
- Docker
- Podman
- LXC (Linux Containers)
- containerd
- CRI-O
### SECTION B: Docker Deep Dive
#### 5.4 What is Docker?
- Docker Overview
- Why We Need Docker
- Docker Use Cases
#### 5.5 How Docker Works
- Docker Architecture
  - Docker Client
  - Docker Daemon (dockerd)
  - Docker Registry
  - Docker Objects
- Docker Engine
#### 5.6 Docker Editions
- Docker Community Edition (CE)
- Docker Enterprise Edition (EE)
#### 5.7 Docker Core Concepts
- Containers
  - Container Lifecycle
  - Container States
- Images
  - Image Layers
  - Base Images
  - Image Tags
- Container Registry
  - Docker Hub
  - AWS ECR
  - Azure Container Registry
  - Private Registries
#### 5.8 Docker Installation
- Installing on Linux (Ubuntu/CentOS)
- Installing on Windows
- Installing on macOS
- Post-installation Steps
#### 5.9 Docker Commands
- **Image Commands**
  - docker pull
  - docker push
  - docker images
  - docker rmi
  - docker build
- **Container Commands**
  - docker run
  - docker start/stop
  - docker ps
  - docker exec
  - docker logs
  - docker rm
  - docker inspect
- **Network Commands**
  - docker network ls
  - docker network create
  - docker network connect
- **Volume Commands**
  - docker volume create
  - docker volume ls
  - docker volume rm
### SECTION C: Dockerfile & YAML
#### 5.10 Writing Dockerfiles
- FROM instruction
- RUN instruction
- COPY/ADD instructions
- WORKDIR instruction
- ENV instruction
- EXPOSE instruction
- CMD instruction
- ENTRYPOINT instruction
- Best Practices for Dockerfiles
#### 5.11 Docker Compose
- What is Docker Compose?
- docker-compose.yml structure
- Services, Networks, Volumes
- Docker Compose Commands
#### 5.12 YAML Basics
- YAML Syntax
- Key-Value Pairs
- Lists and Dictionaries
- Indentation Rules
- YAML vs JSON
### SECTION D: Container Orchestration
#### 5.13 What is Container Orchestration?
- Why Orchestration is Needed
- Orchestration Tools Overview
  - Kubernetes
  - Docker Swarm
  - Apache Mesos
- Key Orchestration Concepts
  - Scheduling
  - Scaling
  - Self-healing
  - Load Balancing
### SECTION E: Kubernetes Administration
#### 5.14 Kubernetes Overview
- What is Kubernetes (K8s)?
- History of Kubernetes
- Kubernetes vs Docker Swarm
- Kubernetes Use Cases
#### 5.15 Kubernetes Architecture
- Control Plane Components
  - API Server (kube-apiserver)
  - etcd
  - Scheduler (kube-scheduler)
  - Controller Manager
- Worker Node Components
  - kubelet
  - kube-proxy
  - Container Runtime
#### 5.16 Kubernetes Resource Model
- Namespaces
- Labels and Selectors
- Annotations
- Resource Quotas
#### 5.17 Kubernetes Orchestration
- Pods
  - What is a Pod?
  - Single Container Pods
  - Multi-container Pods
  - Pod Lifecycle
- Deployments
  - Creating Deployments
  - Rolling Updates
  - Rollbacks
- Services
  - ClusterIP
  - NodePort
  - LoadBalancer
- ConfigMaps and Secrets
- Persistent Volumes (PV)
- Persistent Volume Claims (PVC)
#### 5.18 Creating a Cluster
- Using kubeadm
- Using Minikube (Local)
- Using Cloud Managed Services
#### 5.19 IBM Cloud IKS
- What is IKS (IBM Kubernetes Service)?
- Setting up IKS
- Managing IKS Clusters
#### 5.20 Deploy MW Application on Kubernetes/IKS
- Preparing Application
- Creating Deployment YAML
- Creating Service YAML
- Deploying and Verifying
### ✅ Hands-On Practice Goals
- [ ] Install Docker on Linux
- [ ] Pull and run a Docker container
- [ ] Build a custom Docker image using Dockerfile
- [ ] Push image to Docker Hub/registry
- [ ] Write Docker Compose YAML
- [ ] Create a Kubernetes cluster using Minikube
- [ ] Deploy a pod and deployment
- [ ] Create a Kubernetes service
- [ ] Deploy MW application on IKS
---
## 📦 MODULE 6: ITIL Concepts
> **Duration:** 2 Days | **Format:** Lecture + Hands-On
### 6.1 ITIL Foundation
- What is ITIL?
  - Definition
  - Benefits of ITIL
- History of ITIL
  - ITIL v1, v2, v3
  - ITIL 4 (Current Version)
- Purpose and Evolution
- Guiding Principles of ITIL 4
  - Focus on Value
  - Start Where You Are
  - Progress Iteratively with Feedback
  - Collaborate and Promote Visibility
  - Think and Work Holistically
  - Keep it Simple and Practical
  - Optimize and Automate
### 6.2 Four Dimensions of Service Management
- Organizations and People
- Information and Technology
- Partners and Suppliers
- Value Streams and Processes
### 6.3 Service Value Chain
- Plan
- Improve
- Engage
- Design & Transition
- Obtain/Build
- Deliver & Support
### 6.4 ITIL Practice Groups
- General Management Practices
- Service Management Practices
- Technical Management Practices
### 6.5 Six Key ITIL Practices
#### Practice 1: Service Level Management (SLM)
- SLA (Service Level Agreement)
  - Definition
  - Components of SLA
  - SLA Examples
- SLO (Service Level Objective)
  - Definition
  - SLO vs SLA
- OLA (Operational Level Agreement)
  - Definition
  - OLA vs SLA
#### Practice 2: Service Desk
- SPOC (Single Point of Contact)
- Incident Logging
- Incident Categorization
- Incident Prioritization
  - P1 (Critical)
  - P2 (High)
  - P3 (Medium)
  - P4 (Low)
#### Practice 3: Service Request Management
- Service Catalogue
- Standard Service Requests
- Request Fulfillment
- Request Approval
  - Approval Workflows
  - Approval Authorities
#### Practice 4: Incident Management
- Identification
- Classification
- Prioritization
- Resolution
- Closure
  - Closure Categories
  - Customer Confirmation
#### Practice 5: Problem Management
- Problem Identification
- RCA (Root Cause Analysis)
  - 5 Whys Technique
  - Fishbone Diagram
  - Timeline Analysis
- KEDB (Known Error Database)
- Workaround
- Proactive Problem Management
- Problem Closure
#### Practice 6: Change Management
- Change Request
- CAB (Change Advisory Board)
- Change Modes
- Assessment
- Implementation
- PIR (Post Implementation Review)
- Types of Changes
  - Standard Change (Pre-approved, low risk)
  - Normal Change (Requires CAB approval)
  - Emergency Change (ECAB - Emergency CAB)
### 6.6 ServiceNow Tool
- Overview of ServiceNow
- Incident Management in ServiceNow
- Change Management in ServiceNow
- Service Catalogue in ServiceNow
### ✅ Hands-On Practice Goals
- [ ] Differentiate SLA vs SLO vs OLA
- [ ] Create an incident lifecycle flowchart
- [ ] Draft a change request document
- [ ] Understand complete lifecycle of Incident and Change Management
- [ ] Explore ServiceNow demo
---
# 🟨 WEEK 3: AWS CORE SERVICES
---
## 📦 MODULE 7: Introduction to Cloud Computing, AWS & Amazon EC2
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 7.1 Cloud Computing Overview (AWS Perspective)
- What is Cloud Computing?
- Why AWS?
### 7.2 AWS Global Infrastructure
- Regions
  - What is an AWS Region?
  - How to Choose a Region
  - Current AWS Regions
- Availability Zones (AZs)
  - What is an AZ?
  - How AZs provide High Availability
- Edge Locations
  - Used for CloudFront CDN
- Local Zones
### 7.3 AWS Free Tier
- Types of Free Tier Offers
  - Always Free
  - 12 Months Free
  - Trials
- Free Tier Limits to Know
### 7.4 Amazon EC2 (Elastic Compute Cloud)
#### Introduction to EC2
- What is EC2?
- EC2 Use Cases
#### EC2 Instance Types
- General Purpose (t3, m5)
- Compute Optimized (c5)
- Memory Optimized (r5)
- Storage Optimized (i3)
- GPU Instances (p3, g4)
#### Launching EC2 Instance
- Choosing AMI (Amazon Machine Image)
- Selecting Instance Type
- Configuring Instance Details
- Adding Storage (EBS)
- Adding Tags
- Configuring Security Groups
- Key Pair Setup
#### EC2 Bootstrapping
- What is UserData?
- Writing UserData Scripts
#### Security Groups
- What are Security Groups?
- Inbound and Outbound Rules
- Security Groups vs NACLs
#### Elastic IP
- What is an Elastic IP?
- Allocating and Associating Elastic IP
- Cost Considerations
#### Elastic Load Balancing
- ALB (Application Load Balancer)
- NLB (Network Load Balancer)
- CLB (Classic Load Balancer)
#### Amazon EC2 Auto Scaling
- What is Auto Scaling?
- Auto Scaling Groups (ASG)
- Launch Templates
- Scaling Policies
  - Target Tracking Scaling
  - Step Scaling
  - Scheduled Scaling
- Observing Scale-out Events
### ✅ Hands-On Labs
- [ ] Set up AWS Free Tier account
- [ ] Explore AWS Management Console
- [ ] Launch EC2 with bootstrapping (UserData)
- [ ] Configure autoscaling policy and observe scale-outs
- [ ] SSH into the instance using key pair
- [ ] Terminate the instance
---
## 📦 MODULE 8: Amazon S3 & AWS IAM
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 8.1 Amazon S3 (Simple Storage Service)
#### Introduction to S3
- What is S3?
- S3 Key Features
- S3 Use Cases
#### Buckets and Objects
- What is a Bucket?
- Bucket Naming Rules
- What is an Object?
- Object Keys
- Object Metadata
#### S3 Storage Classes
- S3 Standard
- S3 Intelligent-Tiering
- S3 Standard-IA (Infrequent Access)
- S3 One Zone-IA
- S3 Glacier Instant Retrieval
- S3 Glacier Flexible Retrieval
- S3 Glacier Deep Archive
#### Permissions and Access Control
- Bucket Policies
- ACLs (Access Control Lists)
- Block Public Access Settings
- Pre-signed URLs
### 8.2 AWS IAM (Identity and Access Management)
#### Introduction to IAM
- What is IAM?
- Why IAM is Critical
#### IAM Users
- Creating IAM Users
- Programmatic vs Console Access
- Access Keys
#### IAM Groups
- What are Groups?
- Assigning Users to Groups
#### IAM Roles
- What are Roles?
- Role vs User
- Service Roles
- Cross-Account Roles
#### IAM Policies
- AWS Managed Policies
- Customer Managed Policies
- Inline Policies
- Policy Structure (JSON)
  - Effect (Allow/Deny)
  - Action
  - Resource
  - Condition
- Policy Evaluation Logic
#### Trusted Entities
- Trust Policy
- Principal
#### IAM Best Practices
- Root Account Protection
- Least Privilege Principle
- Enable MFA
- Rotate Access Keys
- Use Roles for Applications
### ✅ Hands-On Labs
- [ ] Create an S3 bucket
- [ ] Upload and manage objects
- [ ] Set bucket policies
- [ ] Create IAM users and groups
- [ ] Attach policies to users and groups
- [ ] Configure MFA (Multi-Factor Authentication)
---
## 📦 MODULE 9: AWS VPC (Virtual Private Cloud)
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 9.1 Introduction to VPC
- What is a VPC?
- Default VPC vs Custom VPC
- VPC CIDR Blocks
### 9.2 Subnets
- Public Subnets
  - Internet Gateway Attachment
  - Public IP Assignment
- Private Subnets
  - No Direct Internet Access
  - NAT Gateway for Outbound
### 9.3 Route Tables
- Main Route Table
- Custom Route Tables
- Route Table Associations
- Routes Configuration
### 9.4 Internet Gateway (IGW)
- Attaching IGW to VPC
- Route Table Entry for IGW
### 9.5 NAT Gateway
- What is NAT Gateway?
- NAT Gateway vs NAT Instance
- Placement in Public Subnet
### 9.6 Transit Gateways
- What is Transit Gateway?
- Hub-and-Spoke Architecture
- Transit Gateway Attachments
### 9.7 Security Groups vs NACLs
- **Security Groups**
  - Stateful
  - Instance Level
  - Allow Rules Only
- **NACLs (Network ACLs)**
  - Stateless
  - Subnet Level
  - Allow and Deny Rules
  - Rule Evaluation Order
### 9.8 VPC Peering
- What is VPC Peering?
- Peering Connection Setup
- Route Table Updates
- Limitations (No Transitive Peering)
### 9.9 VPC Endpoints
- What are VPC Endpoints?
- Gateway Endpoints (S3, DynamoDB)
- Interface Endpoints (PrivateLink)
- Use Cases for Endpoints
### ✅ Hands-On Labs
- [ ] Create a VPC with public and private subnets
- [ ] Configure a security group and NACL
- [ ] Launch instances in Public subnet
- [ ] Launch instances in Private subnet
- [ ] Observe differences between Public and Private subnet instances
- [ ] Create a Lambda function within private subnet
- [ ] Access STS service from Lambda
---
## 📦 MODULE 10: Amazon RDS (Relational Database Service)
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 10.1 Introduction to RDS
- What is RDS?
- Why Managed Database Service?
- RDS vs Self-Managed DB on EC2
### 10.2 Supported Database Engines
- Amazon Aurora (MySQL & PostgreSQL compatible)
- PostgreSQL
- MySQL
- MariaDB
- Oracle
- Microsoft SQL Server
### 10.3 Launching and Managing RDS Instances
- DB Instance Classes
- Storage Types
  - General Purpose SSD (gp2/gp3)
  - Provisioned IOPS SSD (io1)
  - Magnetic
- VPC and Subnet Group Configuration
- Security Groups for RDS
- Parameter Groups
- Option Groups
### 10.4 RDS Multi-AZ Deployments
- What is Multi-AZ?
- How Failover Works
- Primary and Standby Instances
- Benefits (High Availability)
### 10.5 Read Replicas
- What are Read Replicas?
- Read Replicas vs Multi-AZ
- Cross-Region Read Replicas
### 10.6 Backup and Restore
- Automated Backups
  - Backup Window
  - Retention Period
- Manual Snapshots
  - Creating Snapshots
  - Restoring from Snapshots
- Point-in-Time Recovery
### ✅ Hands-On Labs
- [ ] Create an RDS instance (PostgreSQL)
- [ ] Configure VPC and Security Group for RDS
- [ ] Connect to the RDS instance from EC2
- [ ] Perform a backup
- [ ] Restore from backup
---
## 📦 MODULE 11: Amazon Route 53
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 11.1 Introduction to Route 53
- What is Route 53?
- Route 53 as DNS Service
- Route 53 as Domain Registrar
### 11.2 DNS Basics
- How DNS Works
- DNS Resolution Process
- TTL (Time to Live)
- DNS Record Types
  - A Record (IPv4)
  - AAAA Record (IPv6)
  - CNAME Record
  - MX Record
  - TXT Record
  - NS Record
  - SOA Record
### 11.3 Hosted Zones
- Public Hosted Zones
- Private Hosted Zones
### 11.4 Configuring DNS Zones and Records
- Creating Hosted Zone
- Adding DNS Records
- Alias vs CNAME Records
### 11.5 Health Checks
- What are Health Checks?
- Types of Health Checks
  - HTTP/HTTPS Health Checks
  - TCP Health Checks
  - Calculated Health Checks
- Health Check Alerts
### 11.6 Routing Policies
- Simple Routing Policy
- Weighted Routing Policy
- Latency-Based Routing Policy
- Failover Routing Policy
- Geolocation Routing Policy
- Geoproximity Routing Policy
- Multivalue Answer Routing Policy
### ✅ Hands-On Labs
- [ ] Register a domain with Route 53
- [ ] Create and configure a hosted zone
- [ ] Set up DNS records (A, CNAME, etc.)
- [ ] Implement a simple routing policy
- [ ] Configure health checks
---
# 🟧 WEEK 4: AWS ADVANCED SERVICES
---
## 📦 MODULE 12: Resilient Serverless & Scalable Architectures
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 12.1 AWS Lambda
#### Introduction to Lambda
- What is Serverless?
- What is AWS Lambda?
- Lambda Use Cases
#### Creating Lambda Functions
- Supported Runtimes (Python, Node.js, Java, Go)
- Function Code
- Handler Configuration
- Memory and Timeout Settings
- Environment Variables
#### Event Sources and Triggers
- S3 Events
- API Gateway
- DynamoDB Streams
- SNS/SQS
- CloudWatch Events
- Scheduled Events
### 12.2 Reliability and Business Continuity
#### RDS Multi-AZ
- Failover Mechanism
- Testing Failover
#### Route 53 Routing Policies for HA
- Failover Routing
- Latency-based Routing
- Weighted Routing
#### S3 for Data Protection
- S3 Versioning
  - Enabling Versioning
  - Version Management
- Cross-Region Replication (CRR)
  - Setting up CRR
  - CRR Use Cases
#### AWS Backup
- What is AWS Backup?
- Centralized Data Protection
- Backup Plans and Vaults
### 12.3 Disaster Recovery Strategies
- 4 DR Strategies
  - Backup & Restore (RTO/RPO: Hours)
  - Pilot Light (RTO/RPO: Minutes)
  - Warm Standby (RTO/RPO: Minutes)
  - Multi-Site Active/Active (RTO/RPO: Real-time)
- RTO (Recovery Time Objective)
- RPO (Recovery Point Objective)
### ✅ Hands-On Labs
- [ ] Create a simple Lambda function (Python/Node.js)
- [ ] Trigger Lambda using S3 events
- [ ] Test Lambda invocation
- [ ] Set up S3 versioning
- [ ] Configure Cross-Region Replication
---
## 📦 MODULE 13: Amazon DynamoDB & Amazon CloudFront
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 13.1 Amazon DynamoDB
#### Introduction to DynamoDB
- What is DynamoDB?
- NoSQL vs SQL
- DynamoDB Use Cases
#### Tables, Items, and Attributes
- Tables Overview
- Items (Rows)
- Attributes (Columns)
#### Primary Keys
- Partition Key (Simple Primary Key)
- Composite Key (Partition + Sort Key)
#### Indexes
- Local Secondary Index (LSI)
- Global Secondary Index (GSI)
#### DynamoDB Capacity Modes
- On-Demand Mode
- Provisioned Mode
#### DynamoDB Streams and Triggers
- What are DynamoDB Streams?
- Stream Record Types
- Triggering Lambda from DynamoDB Streams
### 13.2 Amazon CloudFront
#### Introduction to CloudFront
- What is CDN?
- What is CloudFront?
- CloudFront Benefits
#### Distributions and Edge Locations
- What is a Distribution?
- Origin Servers
- Edge Locations Worldwide
#### Creating and Configuring Distributions
- Origin Configuration
- Cache Behavior Settings
- TTL Settings
- Viewer Protocol Policy
#### Integrating CloudFront
- CloudFront with S3
  - S3 as Origin
  - OAI (Origin Access Identity)
- CloudFront with EC2
  - EC2/ALB as Origin
  - Custom Headers
### ✅ Hands-On Labs
- [ ] Create a DynamoDB table
- [ ] Perform CRUD operations on DynamoDB
- [ ] Set up a DynamoDB Stream
- [ ] Create a CloudFront distribution
- [ ] Serve content from S3 bucket through CloudFront
---
## 📦 MODULE 14: AWS CloudFormation & Security Best Practices
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 14.1 AWS CloudFormation
#### Introduction to CloudFormation
- What is IaC (Infrastructure as Code)?
- What is CloudFormation?
- CloudFormation Benefits
#### Creating and Managing Stacks
- What is a Stack?
- Creating Stacks via Console
- Creating Stacks via CLI
- Stack Status Types
#### Writing CloudFormation Templates
- Template Structure
  - AWSTemplateFormatVersion
  - Description
  - Parameters
  - Mappings
  - Conditions
  - Resources (Mandatory)
  - Outputs
- Resource Types
- Intrinsic Functions
  - Ref
  - Fn::GetAtt
  - Fn::Join
  - Fn::Sub
- CloudFormation YAML vs JSON
#### Best Practices for IaC
- Use Parameters
- Use Nested Stacks
- Version Control Templates
- Validate Templates Before Deploying
#### Deployment Strategies
- Blue/Green Deployments
  - What is Blue/Green?
  - Implementation with CloudFormation
- Rolling Deployments
  - What is Rolling Deployment?
  - Implementation
### 14.2 Security Best Practices
#### AWS Security Overview
- Shared Responsibility Model
- Security Pillars
#### AWS KMS (Key Management Service)
- What is KMS?
- Customer Master Keys (CMK)
- KMS Key Rotation
- Encrypting Services with KMS
  - S3 Encryption
  - EBS Encryption
  - RDS Encryption
- KMS Key Policies
#### AWS Trusted Advisor
- What is Trusted Advisor?
- Check Categories
  - Cost Optimization
  - Performance
  - Security
  - Fault Tolerance
  - Service Limits
- Acting on Recommendations
### ✅ Hands-On Labs
- [ ] Create a CloudFormation stack
- [ ] Write a basic CloudFormation template
- [ ] Update a stack
- [ ] Delete a stack
- [ ] Enable AWS Trusted Advisor
- [ ] Explore security checks and recommendations
- [ ] Implement basic security practices using KMS
---
## 📦 MODULE 15: Monitoring & Management Tools
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 15.1 Amazon CloudWatch
#### Introduction to CloudWatch
- What is CloudWatch?
- CloudWatch Components
#### Metrics
- Default AWS Metrics
- Custom Metrics
- Metric Math
#### Alarms
- Creating CloudWatch Alarms
- Alarm States (OK, ALARM, INSUFFICIENT_DATA)
- Actions (SNS, Auto Scaling, EC2)
#### CloudWatch Logs
- Log Groups
- Log Streams
- Log Insights
#### CloudWatch Dashboards
- Creating Dashboards
- Adding Widgets
### 15.2 AWS CloudTrail
- What is CloudTrail?
- Event History
- Trails Configuration
- Management vs Data Events
- CloudTrail with S3 and CloudWatch Logs
### 15.3 AWS Config
- What is AWS Config?
- Configuration Recorder
- Config Rules
  - AWS Managed Rules
  - Custom Rules (Lambda)
- Conformance Packs
### 15.4 Amazon GuardDuty
- What is GuardDuty?
- Threat Detection Sources
  - VPC Flow Logs
  - CloudTrail Logs
  - DNS Logs
- GuardDuty Findings
### 15.5 Amazon Inspector
- What is Inspector?
- Inspector v2 Features
- EC2 Instance Scanning
- Container Image Scanning
### 15.6 AWS Systems Manager (SSM)
- What is SSM?
- SSM Agent
- Session Manager (No SSH needed)
- Parameter Store
- Patch Manager
- Run Command
### 15.7 AWS X-Ray
- What is X-Ray?
- Distributed Tracing
- X-Ray Daemon
- Service Map
- Traces and Segments
### ✅ Hands-On Labs
- [ ] Set up CloudWatch alarms for EC2
- [ ] Explore CloudTrail logs
- [ ] Configure AWS Config rules
- [ ] Enable GuardDuty
- [ ] Use SSM Session Manager to connect to EC2
---
## 📦 MODULE 16: AWS Capstone Project & Final Review
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 16.1 Project: Static Website with Multiple AWS Services
#### Project Architecture
| Service | Purpose |
|---------|---------|
| S3 | Static Website Hosting |
| CloudFront | Content Delivery |
| Route 53 | DNS Management |
| IAM | Access Control |
| CloudWatch | Monitoring |
| Certificate Manager | SSL |
#### Implementation Steps
- **Step 1:** Create S3 Bucket
  - Enable Static Website Hosting
  - Upload Website Files
- **Step 2:** Configure CloudFront
  - Create Distribution
  - Point to S3 Origin
- **Step 3:** Set up Route 53
  - Create Hosted Zone
  - Point Domain to CloudFront
- **Step 4:** Apply Security
  - Bucket Policy
  - IAM Roles
- **Step 5:** Configure Monitoring
  - CloudWatch Dashboards
  - Alarms
### 16.2 Final Review
- AWS Service Summary
- Q&A Session
- Feedback
- Next Steps
---
# 🟩 WEEK 5: MICROSOFT AZURE ADMINISTRATION (AZ-104)
---
## 📦 MODULE 17: Administer Identity (Microsoft Entra ID)
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 17.1 Introduction to Microsoft Entra ID
- What is Microsoft Entra ID? *(Formerly Azure Active Directory)*
- Entra ID Concepts
  - Tenants
  - Directories
  - Subscriptions
- Entra ID vs Active Directory Domain Services
  - Key Differences
  - Cloud-based vs On-premises
  - Protocols (OAuth, SAML vs Kerberos, LDAP)
### 17.2 Microsoft Entra ID Editions
- Free
- Microsoft 365 Apps
- Premium P1
- Premium P2
### 17.3 Device Identities
- Azure AD Registered
- Azure AD Joined
- Hybrid Azure AD Joined
### 17.4 User Accounts
- Creating Users
- User Properties
- Guest Users (B2B)
- Managing Users
### 17.5 Bulk Operations
- Bulk Create Users
- Bulk Invite Users
- Bulk Delete Users
### 17.6 Group Accounts
- Security Groups
- Microsoft 365 Groups
- Assigned vs Dynamic Membership
- Group Management
### 17.7 Self-Service Password Reset (SSPR)
- What is SSPR?
- Enabling SSPR
- Authentication Methods
### 17.8 Multi-Tenant Environments
- What is Multi-Tenancy?
- B2B Collaboration
- External Identities
### ✅ Hands-On Labs
- [ ] Create Azure account and set up Entra ID
- [ ] Create and manage users
- [ ] Perform bulk user operations
- [ ] Create security groups
- [ ] Configure SSPR
- [ ] Set up MFA
---
## 📦 MODULE 18: Administer Governance & Compliance
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 18.1 Managing Subscriptions
- What is an Azure Subscription?
- Types of Subscriptions
- Management Groups
- Subscription Hierarchy
### 18.2 Resource Groups and Limits
- What is a Resource Group?
- Creating Resource Groups
- Resource Group Best Practices
- Azure Resource Limits
### 18.3 Azure Hierarchy
- Management Groups
- Subscriptions
- Resource Groups
- Resources
### 18.4 Azure Resource Tags
- What are Tags?
- Applying Tags
- Tag Policies
- Cost Management with Tags
### 18.5 Azure Resource Locks
- What are Resource Locks?
- CanNotDelete Lock
- ReadOnly Lock
- Applying and Removing Locks
### 18.6 Cost Management
- Azure Cost Management Tool
- Budgets and Alerts
- Cost Analysis
- Azure Pricing Calculator
### 18.7 Azure Policy
- What is Azure Policy?
- Policy Definitions
- Policy Assignments
- Policy Effects
  - Deny
  - Audit
  - Append
  - DeployIfNotExists
- Configuring Initiatives (Policy Sets)
### 18.8 Role Based Access Control (RBAC)
- What is Azure RBAC?
- RBAC Components
  - Security Principal
  - Role Definition
  - Scope
- Built-in Roles
  - Owner
  - Contributor
  - Reader
  - User Access Administrator
- Custom Roles
- Azure RBAC vs Microsoft Entra ID Roles
  - Key Differences
  - When to Use Each
### ✅ Hands-On Labs
- [ ] Create management groups
- [ ] Apply resource tags
- [ ] Create resource locks
- [ ] Set up budget alerts
- [ ] Create and assign Azure Policy
- [ ] Configure RBAC roles
---
## 📦 MODULE 19: Administer Azure Resources
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 19.1 Azure Administrator Tools Comparison
- Azure Portal (Web UI)
- Azure CLI
- Azure PowerShell
- Azure Cloud Shell
- Azure REST API
### 19.2 Azure Resource Manager (ARM)
- What is ARM?
- ARM Architecture
- Resource Providers
- Resource Types
- ARM API
### 19.3 ARM Templates
- What are ARM Templates?
- ARM Template Structure
  - $schema
  - contentVersion
  - parameters
  - variables
  - functions
  - resources
  - outputs
- Deploying ARM Templates
  - Via Portal
  - Via CLI
  - Via PowerShell
- ARM Template Best Practices
### 19.4 Azure Bicep
- What is Bicep?
- Bicep vs ARM Templates
- Bicep File Structure
- Deploying Bicep Files
### ✅ Hands-On Labs
- [ ] Use Azure CLI to create resources
- [ ] Write and deploy an ARM template
- [ ] Write a basic Bicep file
- [ ] Compare Portal vs CLI operations
---
## 📦 MODULE 20: Administer Virtual Networking
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 20.1 Creating and Configuring Virtual Networks
- What is Azure VNet?
- VNet Address Space
- Creating VNets
- VNet Best Practices
### 20.2 Subnets
- Creating Subnets
- Subnet Address Ranges
- Reserved IP Addresses in Azure
### 20.3 Private and Public IP Addresses
- Private IP Addresses
  - Dynamic vs Static
  - Allocation
- Public IP Addresses
  - Basic vs Standard SKU
  - Associating Public IPs
### 20.4 Network Security Groups (NSG)
- What is an NSG?
- Inbound and Outbound Rules
- Rule Properties
  - Priority
  - Source/Destination
  - Port
  - Protocol
- NSG Association
  - Subnet Level
  - NIC Level
### 20.5 Application Security Groups (ASG)
- What is an ASG?
- ASG vs NSG
- Using ASGs in NSG Rules
### 20.6 Azure DNS
- Azure Public DNS Zones
- Creating DNS Zones
- Adding DNS Records
- Delegating Domains to Azure DNS
### 20.7 Azure Private DNS Zones
- What are Private DNS Zones?
- Private DNS Zone Links
- Auto-registration
### ✅ Hands-On Labs
- [ ] Create a VNet with multiple subnets
- [ ] Configure NSG rules
- [ ] Create Application Security Groups
- [ ] Set up Azure DNS zones
- [ ] Configure Private DNS zones
---
## 📦 MODULE 21: Administer Intersite Connectivity
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 21.1 Virtual Network Peering
- What is VNet Peering?
- Local VNet Peering
- Global VNet Peering
- Peering Configuration
- Peering Limitations (No Transitive Peering)
### 21.2 VPN Gateway
- What is VPN Gateway?
- VPN Gateway SKUs
- Gateway Subnet
- VPN Types
  - Route-based VPN
  - Policy-based VPN
### 21.3 Site-to-Site VPN
- What is S2S VPN?
- Local Network Gateway
- VPN Connection Setup
- Use Cases
### 21.4 Point-to-Site VPN
- What is P2S VPN?
- Authentication Methods
  - Azure Certificate
  - Azure Entra ID
- VPN Client Configuration
### 21.5 Gateway Transit
- What is Gateway Transit?
- Hub-and-Spoke with Gateway Transit
### 21.6 User Defined Routes (UDR)
- What are UDRs?
- Route Tables
- Custom Routes
- Forcing Traffic Through NVA
### 21.7 Service Endpoints
- What are Service Endpoints?
- Supported Services
- Configuring Service Endpoints
### 21.8 Private Endpoints
- What are Private Endpoints?
- Private Link
- Private Endpoint vs Service Endpoint
- Configuring Private Endpoints
### ✅ Hands-On Labs
- [ ] Configure VNet Peering between two VNets
- [ ] Set up Site-to-Site VPN
- [ ] Configure Point-to-Site VPN
- [ ] Create User Defined Routes
- [ ] Set up Service Endpoints
- [ ] Configure Private Endpoints
---
## 📦 MODULE 22: Administer Network Traffic
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 22.1 Azure Load Balancer
- What is Azure Load Balancer?
- Public vs Internal Load Balancer
- Load Balancer SKUs
  - Basic
  - Standard
- Load Balancer Components
  - Frontend IP Configuration
  - Backend Pool
  - Health Probes
  - Load Balancing Rules
- Session Persistence
  - None (5-tuple Hash)
  - Client IP (2-tuple Hash)
  - Client IP and Protocol (3-tuple Hash)
### 22.2 Azure Application Gateway
- What is Application Gateway?
- Application Gateway vs Load Balancer
- Application Gateway Components
  - Frontend IP
  - Listeners
  - Request Routing Rules
  - Backend Pools
  - HTTP Settings
- Routing Rules
  - Basic Routing
  - Path-based Routing
- WAF (Web Application Firewall)
  - WAF Modes (Detection/Prevention)
  - WAF Rules
### 22.3 Other Load Balancing Solutions
- Azure Front Door
  - Global Load Balancing
  - CDN Capabilities
- Azure Traffic Manager
  - DNS-based Load Balancing
  - Traffic Routing Methods
- Comparison of All LB Solutions
  - When to Use Load Balancer
  - When to Use Application Gateway
  - When to Use Front Door
  - When to Use Traffic Manager
### 22.4 Network Watcher
- What is Network Watcher?
- IP Flow Verify
- Next Hop
- VPN Diagnostics
- NSG Flow Logs
- Connection Troubleshoot
### ✅ Hands-On Labs
- [ ] Create Azure Load Balancer
- [ ] Configure load balancer rules
- [ ] Set up Application Gateway
- [ ] Configure path-based routing
- [ ] Use Network Watcher for troubleshooting
---
## 📦 MODULE 23: Administer Azure Storage
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 23.1 Storage Accounts
- What is an Azure Storage Account?
- Storage Account Types
  - Standard General-Purpose v2
  - Premium Block Blobs
  - Premium File Shares
  - Premium Page Blobs
- Creating Storage Accounts
### 23.2 Storage Redundancy
| Type | Full Form |
|------|----------|
| LRS | Locally Redundant Storage |
| ZRS | Zone-Redundant Storage |
| GRS | Geo-Redundant Storage |
| GZRS | Geo-Zone-Redundant Storage |
| RA-GRS | Read-Access Geo-Redundant Storage |
### 23.3 Accessing Storage Endpoints
- Public Endpoints
- Private Endpoints for Storage
### 23.4 Azure Blob Storage
- What are Containers? (Blob Containers)
- Blob Types
  - Block Blobs
  - Append Blobs
  - Page Blobs
- Uploading and Managing Blobs
### 23.5 Storage Access Tiers
- Hot Tier
- Cool Tier
- Cold Tier
- Archive Tier
### 23.6 Lifecycle Management
- Lifecycle Management Policies
- Transitioning Between Tiers
- Deleting Old Objects
### 23.7 Azure File Share
- What is Azure Files?
- Creating File Shares
- Mounting File Shares
  - On Windows (SMB)
  - On Linux (NFS)
- Azure File Sync
### 23.8 Securing Storage Endpoints
- Firewall and Virtual Network Rules
- Private Endpoints
### 23.9 Storage Security
- Storage Service Encryption (SSE)
  - Microsoft Managed Keys
  - Customer Managed Keys (CMK)
- Azure Disk Encryption (ADE)
### 23.10 Configuring Storage Access
- Storage Account Access Keys
  - Primary and Secondary Keys
  - Key Rotation
- Shared Access Signatures (SAS)
  - Account SAS
  - Service SAS
  - User Delegation SAS
  - SAS Token Parameters
### ✅ Hands-On Labs
- [ ] Create storage account
- [ ] Upload blobs to containers
- [ ] Configure access tiers
- [ ] Set up lifecycle management policies
- [ ] Create and mount Azure File Share
- [ ] Generate SAS tokens
- [ ] Configure storage firewall rules
---
## 📦 MODULE 24: Administer Azure Virtual Machines
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 24.1 Microsoft Entra ID Authentication for VMs
- Entra ID for VM Login
- RBAC for VM Access
### 24.2 Planning VMs
- VM Planning Considerations
  - Region Selection
  - Availability Requirements
  - Networking Requirements
  - Storage Requirements
- VM Sizing Guidelines
### 24.3 Managing VM Sizes
- VM Size Families
  - General Purpose (Dsv3, Dv3)
  - Compute Optimized (Fsv2)
  - Memory Optimized (Esv3, Ev3)
  - Storage Optimized (Lsv2)
  - GPU (NV, NC)
- Resizing VMs
### 24.4 Virtual Machine Storage
- OS Disk
- Data Disks
- Temporary Disk
- Managed vs Unmanaged Disks
- Disk Types
  - Ultra Disk
  - Premium SSD
  - Standard SSD
  - Standard HDD
### 24.5 Creating VMs
- Via Azure Portal
- Via Azure CLI
- Via ARM Template
- VM Configuration Settings
### 24.6 Connecting to VMs
- RDP (Windows VMs)
- SSH (Linux VMs)
- Azure Bastion
  - What is Bastion?
  - Bastion vs Jump Box
- Serial Console
### 24.7 Configuring High Availability
- Availability Sets
  - Fault Domains
  - Update Domains
- Availability Zones
  - Zone-redundant Deployment
  - Zonal Deployment
- SLA Comparison
  - Single VM SLA (99.9%)
  - Availability Set SLA (99.95%)
  - Availability Zone SLA (99.99%)
### 24.8 Virtual Machine Scale Sets (VMSS)
- What is VMSS?
- Scaling Options
  - Manual Scaling
  - Autoscaling
- Scale Set Configuration
- Upgrade Policies
  - Manual
  - Automatic
  - Rolling
- Flexible vs Uniform Orchestration
### ✅ Hands-On Labs
- [ ] Create Windows and Linux VMs
- [ ] Connect to VMs via RDP and SSH
- [ ] Set up Azure Bastion
- [ ] Configure Availability Set
- [ ] Deploy VM Scale Set
- [ ] Configure autoscaling for VMSS
---
# 🟥 WEEK 6: AZURE ADVANCED + DEVOPS + MICROSERVICES
---
## 📦 MODULE 25: Administer PaaS Compute Options
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 25.1 Azure App Service
#### What is App Service?
- App Service Plans
  - Free/Shared Tier
  - Basic Tier
  - Standard Tier
  - Premium Tier
  - Isolated Tier
#### Deploying App Service
- Via Portal
- Via Azure CLI
- Via VS Code
#### Securing App Service
- Authentication/Authorization
- IP Restrictions
- Managed Identity
#### Custom Domains
- Adding Custom Domain
- SSL/TLS Certificates
#### Backup App Service
- Configuring Backups
- Restoring from Backup
#### CI/CD Integration
- GitHub Actions
- Azure DevOps
- Local Git Deployment
#### Deployment Slots
- What are Slots?
- Staging Slot
- Slot Swapping (Blue/Green)
### 25.2 Azure Container Instances (ACI)
- What is ACI?
- ACI vs VMs vs App Service
- Container Groups
  - What are Container Groups?
  - Multi-container Groups
  - Shared Resources
- Deploying Containers to ACI
- ACI Use Cases
### ✅ Hands-On Labs
- [ ] Create and deploy an App Service
- [ ] Configure deployment slots
- [ ] Perform slot swap
- [ ] Set up CI/CD pipeline
- [ ] Deploy container to ACI
- [ ] Create multi-container group
---
## 📦 MODULE 26: Azure Container Apps & Data Protection
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 26.1 Azure Container Apps
- What is Azure Container Apps?
- Container Apps vs ACI vs AKS
- Container Apps Environment
- Deploying Container Apps
- Scaling Container Apps
  - KEDA (Kubernetes Event-driven Autoscaling)
  - HTTP Scaling
- Ingress Configuration
### 26.2 Azure Backup Overview
- What is Azure Backup?
- Azure Backup Architecture
### 26.3 Azure Backup Center
- Centralized Backup Management
- Backup Dashboard
### 26.4 File and Folder Backup
- MARS Agent
- Installing MARS Agent
- Configuring File Backup
### 26.5 Configuring Backup for Azure VMs
- Recovery Services Vault
- Backup Policy
- Enabling VM Backup
- Performing VM Restore
### 26.6 Configuring Backup for Non-Azure VMs
- On-premises VM Backup
- Azure Backup Server (MABS)
### 26.7 Backup Options Comparison
- Azure VM Backup
- MARS Agent
- Azure Backup Server
- DPM (Data Protection Manager)
### 26.8 Soft Delete
- What is Soft Delete?
- Soft Delete for VMs
- Managing Soft Delete
### ✅ Hands-On Labs
- [ ] Deploy Azure Container Apps
- [ ] Configure scaling rules
- [ ] Create Recovery Services Vault
- [ ] Configure VM backup
- [ ] Perform file/folder restore
- [ ] Explore Azure Backup Center
---
## 📦 MODULE 27: Azure Site Recovery & Monitoring
> **Duration:** 1 Day | **Format:** Lecture + Hands-On
### 27.1 Azure Site Recovery (ASR)
- What is ASR?
- ASR Architecture
- Supported Scenarios
  - Azure VM to Azure VM
  - On-premises to Azure
  - On-premises to On-premises
- Replication Configuration
- Recovery Plans
  - Creating Recovery Plans
  - Adding Runbooks
- Failover
  - Test Failover
  - Planned Failover
  - Unplanned Failover
- Failback
### 27.2 Azure Monitor
#### What is Azure Monitor?
- Azure Monitor Architecture
  - Data Sources
  - Data Platform
  - Consumption
#### Azure Activity Logs
- What are Activity Logs?
- Log Categories
- Exporting Activity Logs
#### Log Analytics Workspace
- What is Log Analytics?
- Creating Log Analytics Workspace
- Connecting Data Sources
- Data Retention Settings
#### Querying Log Analytics (KQL)
- Kusto Query Language (KQL) Basics
- Common KQL Operators
  - where
  - project
  - summarize
  - count
  - top
- Sample Queries
  - VM Performance Queries
  - Security Event Queries
  - Custom Log Queries
### ✅ Hands-On Labs
- [ ] Configure ASR for Azure VM
- [ ] Perform test failover
- [ ] Create Recovery Plan
- [ ] Enable Log Analytics Workspace
- [ ] Connect VM to Log Analytics
- [ ] Write basic KQL queries
---
## 📦 MODULE 28: Azure Alerts
> **Duration:** 0.5 Day | **Format:** Lecture
### 28.1 Azure Alerts
- What are Azure Alerts?
- Types of Alerts
  - Metric Alerts
  - Log Alerts
  - Activity Log Alerts
  - Smart Detection Alerts
- Alert Components
  - Alert Rule
  - Action Group
  - Alert Processing Rules
- Creating Metric Alerts
- Creating Log Alerts
- Action Groups
  - Notification Types
    - Email
    - SMS
    - Push Notification
  - Action Types
    - Webhook
    - Logic App
    - Azure Function
    - Automation Runbook
### 28.2 Azure Monitor Workbooks
- What are Workbooks?
- Creating Custom Workbooks
- Sharing Workbooks
---
## 📦 MODULE 29: Microservices & APIs
> **Duration:** 0.5 Day | **Format:** Lecture
### 29.1 What are Microservices?
- Definition
- Monolithic vs Microservices
  - Monolithic Architecture
    - Pros
    - Cons
  - Microservices Architecture
    - Pros
    - Cons
- When to Use Microservices
### 29.2 APIs (Application Programming Interfaces)
- What is an API?
- REST API Basics
  - HTTP Methods (GET, POST, PUT, DELETE)
  - Status Codes (200, 404, 500)
  - JSON Format
- API Gateway
  - What is API Gateway?
  - API Gateway Use Cases
### 29.3 Microservices Architecture
- Service Discovery
- Load Balancing in Microservices
- Circuit Breaker Pattern
- Event-Driven Architecture
- Message Queues (Kafka, RabbitMQ)
### 29.4 Benefits of Microservices
- Independent Deployment
- Technology Diversity
- Fault Isolation
- Scalability
- Team Autonomy
### 29.5 Migration to Microservices
- Strangler Fig Pattern
- Domain-Driven Design (DDD)
- Migration Steps
### 29.6 Real-time Microservices Examples
- Netflix Architecture
- Amazon Architecture
- Uber Architecture
### 29.7 How Microservices Work Together
- Synchronous Communication (REST, gRPC)
- Asynchronous Communication (Message Queues)
- Service Mesh (Istio)
- Containerized Microservices (Kubernetes)
---
## 📦 MODULE 30: Introduction to DevOps
> **Duration:** 0.5 Day | **Format:** Lecture + Hands-On
### 30.1 DevOps Culture
- What is DevOps?
- DevOps vs Traditional IT
- DevOps Principles
  - Collaboration
  - Automation
  - Continuous Improvement
  - Customer-Centric Action
- DevOps Team Structure
### 30.2 DevOps Organization
- Breaking Down Silos
- Dev and Ops Collaboration
- DevSecOps Introduction
### 30.3 DevOps Processes
- Agile Methodology
- Scrum Framework
- Kanban
- Lean Principles
### 30.4 DevOps Automation Concepts
- Infrastructure as Code (IaC)
- Configuration Management
  - Ansible
  - Chef
  - Puppet
- Pipeline Automation
### 30.5 DevOps Measure and Improvement
- Key DevOps Metrics
  - Deployment Frequency
  - Lead Time for Changes
  - Mean Time to Recovery (MTTR)
  - Change Failure Rate
- DORA Metrics
### 30.6 DevOps Lifecycle Phases
#### Continuous Development
- Planning (Jira, Azure Boards)
- Coding (Git, GitHub, Azure Repos)
#### Continuous Integration (CI)
- What is CI?
- CI Tools
  - Jenkins
  - GitHub Actions
  - Azure Pipelines
- Building Code
- Running Automated Tests
#### Continuous Testing
- Unit Testing
- Integration Testing
- Performance Testing
- Security Testing (SAST/DAST)
#### Continuous Delivery
- What is CD?
- CD vs Continuous Deployment
- Release Pipeline
#### Continuous Deployment
- What is Continuous Deployment?
- Deployment Strategies
  - Blue/Green Deployment
  - Canary Deployment
  - Rolling Deployment
- Feature Flags
#### Continuous Monitoring/Feedback
- Application Performance Monitoring
- Log Monitoring
- Feedback Loops
### ✅ Hands-On Practice Goals
- [ ] Set up a basic CI/CD pipeline
- [ ] Create a GitHub Actions workflow
- [ ] Understand deployment strategies
---
## 📦 MODULE 31: Azure Capstone Project & Final Review
> **Duration:** 0.5 Day | **Format:** Hands-On
### 31.1 Project: Integrating Multiple Azure Services
#### Project Architecture
| Service | Purpose |
|---------|---------|
| Azure VNet | Networking Foundation |
| Azure VM / App Service | Compute |
| Azure Storage | Data Layer |
| Azure SQL / Cosmos DB | Database |
| Azure Monitor | Observability |
| Azure Backup | Data Protection |
| Azure Site Recovery | Disaster Recovery |
| RBAC + Policy | Governance |
#### Implementation Steps
- Step 1: Create VNet with Subnets
- Step 2: Deploy VMs or App Service
- Step 3: Configure NSGs
- Step 4: Set up Storage Account
- Step 5: Configure Azure Backup
- Step 6: Set up Monitoring & Alerts
- Step 7: Apply RBAC and Policies
### 31.2 Final Review
- Azure Service Summary
- AZ-104 Exam Tips
- Q&A Session
- Feedback
- Next Steps
---
# 🏆 CERTIFICATION PREPARATION GUIDE
---
## 🎯 AWS Certified SysOps Administrator - Associate (SOA-C02)
| Parameter | Details |
|-----------|---------|
| **Exam Code** | SOA-C02 |
| **Duration** | 180 minutes |
| **Questions** | 65 questions |
| **Passing Score** | 720/1000 |
| **Format** | Multiple choice + Lab exam |
### Exam Domain Breakdown
#### Domain 1: Monitoring, Logging, and Remediation (20%)
- CloudWatch Metrics, Alarms, Dashboards
- CloudTrail Logs
- AWS Config
- Systems Manager
#### Domain 2: Reliability and Business Continuity (16%)
- Backup and Recovery
- High Availability
- Scaling Strategies
- Disaster Recovery
#### Domain 3: Deployment, Provisioning, and Automation (18%)
- EC2, AMIs, Launch Templates
- CloudFormation
- Elastic Beanstalk
- Auto Scaling
#### Domain 4: Security and Compliance (16%)
- IAM, Policies, Roles
- KMS, Secrets Manager
- GuardDuty, Inspector
- VPC Security
#### Domain 5: Networking and Content Delivery (18%)
- VPC, Subnets, Route Tables
- Route 53
- CloudFront
- ELB
#### Domain 6: Cost and Performance Optimization (12%)
- Cost Explorer
- Trusted Advisor
- Right Sizing
- Reserved Instances
---
## 🎯 AZ-104 Microsoft Azure Administrator
| Parameter | Details |
|-----------|---------|
| **Exam Code** | AZ-104 |
| **Duration** | 120 minutes |
| **Questions** | 40-60 questions |
| **Passing Score** | 700/1000 |
| **Format** | Multiple choice, drag-and-drop, case studies |
### Exam Domain Breakdown
#### Manage Azure Identities and Governance (20-25%)
- Manage Microsoft Entra ID
- Manage RBAC
- Azure Policy
- Resource Locks and Tags
#### Implement and Manage Storage (15-20%)
- Storage Accounts
- Blob Storage
- Azure Files
- Storage Security
#### Deploy and Manage Azure Compute Resources (20-25%)
- Azure VMs
- VM Scale Sets
- App Service
- Container Instances
#### Implement and Manage Virtual Networking (15-20%)
- VNet and Subnets
- NSG and ASG
- Load Balancing
- VPN and Peering
#### Monitor and Maintain Azure Resources (10-15%)
- Azure Monitor
- Log Analytics
- Azure Backup
- Azure Site Recovery
---
## 📚 Recommended Certification Path
---
## 📊 Study Timeline Recommendation
| Week | Daily Focus | Hours/Day |
|------|------------|-----------|
| Week 1 | Linux + Cloud Overview + Networking | 8 hours |
| Week 2 | Firewall + Containers + ITIL | 8 hours |
| Week 3 | AWS EC2, S3, IAM, VPC, RDS, Route53 | 8 hours |
| Week 4 | AWS Lambda, DynamoDB, CloudFormation, Monitoring | 8 hours |
| Week 5 | Azure Identity, Governance, Networking, VMs | 8 hours |
| Week 6 | Azure PaaS, Backup, DR, DevOps, MicroServices | 8 hours |
| Week 7-8 | Induction Program | - |
| Week 9-11 | Shadow/OJT + Certification Prep | 2-3 hrs extra |
---
## ✅ Master Checklist
### Foundation Modules (Week 1-2)
- [ ] MODULE 1: Linux Fundamentals
- [ ] MODULE 2: Cloud Overview
- [ ] MODULE 3: Networking Fundamentals
- [ ] MODULE 4: Firewall, Load Balancer, Routing & Proxy
- [ ] MODULE 5: Containers & Kubernetes
- [ ] MODULE 6: ITIL Concepts
### AWS Modules (Week 3-4)
- [ ] MODULE 7: AWS EC2 & Cloud Computing
- [ ] MODULE 8: S3 & IAM
- [ ] MODULE 9: VPC
- [ ] MODULE 10: RDS
- [ ] MODULE 11: Route 53
- [ ] MODULE 12: Lambda & Serverless
- [ ] MODULE 13: DynamoDB & CloudFront
- [ ] MODULE 14: CloudFormation & Security
- [ ] MODULE 15: Monitoring & Management
- [ ] MODULE 16: AWS Capstone Project
### Azure Modules (Week 5-6)
- [ ] MODULE 17: Entra ID & Identity
- [ ] MODULE 18: Governance & Compliance
- [ ] MODULE 19: Azure Resources
- [ ] MODULE 20: Virtual Networking
- [ ] MODULE 21: Intersite Connectivity
- [ ] MODULE 22: Network Traffic
- [ ] MODULE 23: Azure Storage
- [ ] MODULE 24: Azure VMs
- [ ] MODULE 25: PaaS Compute
- [ ] MODULE 26: Container Apps & Data Protection
- [ ] MODULE 27: Site Recovery & Monitoring
- [ ] MODULE 28: Azure Alerts
- [ ] MODULE 29: Microservices
- [ ] MODULE 30: DevOps
- [ ] MODULE 31: Azure Capstone Project
### Certifications
- [ ] AWS SOA-C02 Cleared
- [ ] AZ-104 Cleared
---
## 🛠️ Tools & Resources Summary
| Resource | Link | Purpose |
|----------|------|---------|
| Linux Course (Udemy) | https://ibm-learning.udemy.com/course/complete-linux-training-course-to-get-your-dream-it-job/ | Linux Fundamentals |
| RHEL Training | https://yourlearning.ibm.com/activity/SMT-3862 | Red Hat Linux |
| Cloud Lab Credits | https://w3.ibm.com/w3publisher/cloud-lab-request-aws-azure-google | $10 AWS/Azure/GCP |
| AWS Free Tier | https://aws.amazon.com/free | AWS Practice |
| Azure Free Account | https://azure.microsoft.com/free | Azure Practice |
| AWS Documentation | https://docs.aws.amazon.com | AWS Reference |
| Azure Documentation | https://docs.microsoft.com/azure | Azure Reference |
| AWS Skill Builder | https://skillbuilder.aws | AWS Exam Prep |
| Microsoft Learn | https://learn.microsoft.com | Azure Exam Prep |
---
## 💡 Pro Tips
> 1. **Always do hands-on labs** after each module
> 2. **Use the $10 sandbox credits wisely** - plan before you deploy
> 3. **Take notes during shadow/OJT** on real-world scenarios
> 4. **Practice KQL queries daily** during Azure week
> 5. **Revise ITIL concepts regularly** - they appear in real work
> 6. **Join AWS/Azure community forums** for exam tips
> 7. **Use AWS Skill Builder and Microsoft Learn** for free practice tests
> 8. **Attempt mock exams** at least 2 weeks before actual exam
> 9. **Review weak areas** from mock exam results
> 10. **Document your hands-on work** for future reference
---
*End of Complete Study Plan - All 31 Modules*
*Total Duration: 30 Training Days | Target: AWS SOA-C02 + AZ-104*
