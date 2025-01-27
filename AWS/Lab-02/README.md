# Lab 2: Building Your Amazon VPC Infrastructure

## Objective
The purpose of this lab was to:
- Build a VPC architecture in AWS with public and private subnets, an internet gateway, and a NAT gateway.
- Launch EC2 instances in public and private subnets.
- Demonstrate an understanding of networking, routing, and security groups.

---

## Architecture Diagram
Below is the architecture I created during this lab:



---

## What I Did
Step 1: Created an Amazon VPC
- Created a new VPC named **Lab VPC** with a CIDR block of `10.0.0.0/16`.
- Enabled **DNS hostnames** to assign DNS names to EC2 instances in the VPC.
- Verified the VPC state to ensure it was `Available`.

#### Command:
```bash
aws ec2 create-vpc --cidr-block 10.0.0.0/16 --tag-specifications 'ResourceType=vpc,Tags=[{Key=Name,Value=Lab VPC}]'
```
#### Command:
```bash
Step 2: Created Public and Private Subnets
Public Subnet: Created a public subnet with CIDR block 10.0.0.0/24 and enabled auto-assignment of public IPs for instances.
Private Subnet: Created a private subnet with CIDR block 10.0.2.0/23 for isolated resources.
```
#### Command:
```bash
aws ec2 create-subnet --vpc-id vpc-xxxxxxxx --cidr-block 10.0.0.0/24 --availability-zone us-east-1a --tag-specifications 'ResourceType=subnet,Tags=[{Key=Name,Value=Public Subnet}]'
```
