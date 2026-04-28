# terraform AWS VPC Module Customised

This module is going to create the following resources. For HA we are going to get first 2 AZ

* vpc
* internet gateway associated with vpc
* 2 public subnets
* 2 private subnets
* 2 database subnets
* database subnet groups
* eip
* nat gateway
* Public route table
* private route table
* database route table
* routes
* route table associations with subnets
* peering with default vpc(if required)
* peering routes in acceptor and requester route tables

# inputs
Project_name (mandatory): user must supply their project name.
environment (mandatory): user must supply environment
vpc_cidr (mandatory): user must supply vpc cidr
enable _dns_hostnames (optional): defaults to true
common_tags (optional)
vpc_tags(optional)
igw_tags(optional)
public_subnet_cidrs (mandatory)
public_subnet_tags(optional)
private_subnet_cidrs (mandatory)
private_subnet_tags(optional)
database_subnet_cidrs(mandatory)
database_subnet_tags(optional)
db_subnet_group_tags(optional)
nat_gateway_tags (optional)
public_route_table_tags(optional)
private_route_table_tags(optional)
database_route_table_tags(optional)
is_peering_required(optional)
vpc_peering_tags(optional)


#  AWS VPC Networking using Terraform

##  Project Overview
This project demonstrates Infrastructure as Code (IaC) implementation using Terraform to provision and manage AWS Virtual Private Cloud (VPC) networking components.

It includes the setup of core networking resources such as subnets, route tables, internet gateway, and associated configurations to simulate a real-world cloud network architecture.

The objective is to build a scalable, secure, and production-ready network foundation for application deployments.

---

##  Objectives

- Provision AWS VPC using Terraform
- Configure public and private subnets
- Enable internet connectivity via Internet Gateway
- Implement routing using route tables
- Simulate real-world cloud networking architecture

---

##  Tech Stack

- Infrastructure as Code: Terraform
- Language: HCL (HashiCorp Configuration Language)
- Cloud Platform: AWS
- Networking Components: VPC, Subnets, Route Tables, IGW
- Version Control: Git

---

##  Architecture

- VPC: Isolated network environment
- Subnets:
  - Public Subnet (internet-facing resources)
  - Private Subnet (internal resources)
- Internet Gateway: Enables external connectivity
- Route Tables: Control traffic routing
- Associations: Link subnets with route tables

This architecture follows standard AWS networking design practices for scalable and secure environments.

---

##  Repository Structure
├── main.tf
├── variables.tf
├── outputs.tf
├── provider.tf
├── terraform.tfvars
└── README.md


---

##  Workflow

1. Define VPC and networking components in Terraform
2. Initialize Terraform environment
3. Validate configuration
4. Generate execution plan
5. Apply configuration to create infrastructure
6. Manage state for future updates

---

##  Key Features

- Automated VPC provisioning
- Public and private subnet architecture
- Controlled internet access via IGW
- Structured routing configuration
- Scalable network design

---

##  Engineering Highlights

### Network Isolation
VPC provides a logically isolated environment for resources.

### Security
Private subnets prevent direct internet exposure of sensitive components.

### Scalability
Subnet design supports expansion across availability zones.

### Traffic Control
Route tables enable fine-grained traffic management.

---

##  Execution Steps

### Initialize Terraform
```bash
terraform init
Validate Configuration
terraform validate
Plan Infrastructure
terraform plan
Apply Configuration
terraform apply
Destroy Infrastructure
terraform destroy

Real-World Use Cases
Foundation for 3-tier architecture deployments
Hosting secure cloud applications
Network segmentation for enterprise systems
Supporting scalable DevOps environments


Challenges & Solutions
Challenge	Solution
Network misconfiguration	Structured Terraform definitions
Internet access issues	Proper IGW and routing setup
Subnet design complexity	Separated public/private subnets
Debugging connectivity	Validated routing and associations


Future Enhancements
Add NAT Gateway for private subnet internet access
Implement multi-AZ architecture
Integrate with security groups and NACLs
Convert into reusable Terraform modules
Combine with EC2 and load balancer setup


Key Learnings
VPC is the foundation of AWS infrastructure
Proper subnet and routing design is critical
Terraform ensures consistent infrastructure provisioning
Infrastructure as Code improves scalability and reliability
