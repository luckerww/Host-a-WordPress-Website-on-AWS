Host a WordPress Website on AWS

I recently completed a DevOps project where I hosted a WordPress website (https://www.luckerww.com/) on AWS using various AWS resources to ensure high availability, scalability, and security. This repository contains the reference architecture diagram and scripts used to deploy the WordPress application on an EC2 instance.

Project Overview

The project involved setting up a robust and secure environment for hosting a WordPress website on AWS by configuring various AWS services, such as EC2, VPC, and RDS. Below is an overview of the architecture and the AWS resources used.

![IMG_7731](https://github.com/user-attachments/assets/b43193cd-3f88-494a-afb9-810f35b70318)


Architecture Components

	•	Virtual Private Cloud (VPC): Configured a VPC with both public and private subnets across two Availability Zones (AZs) to ensure high availability and fault tolerance.
	•	Internet Gateway: Deployed an Internet Gateway to enable connectivity between instances within the VPC and the Internet.
	•	Security Groups: Established Security Groups to act as network firewalls, controlling inbound and outbound traffic to instances.
	•	Availability Zones: Utilized two Availability Zones to enhance system reliability and fault tolerance.
	•	Subnets:
	•	Public Subnets: Used for infrastructure components such as the NAT Gateway and Application Load Balancer.
	•	Private Subnets: Positioned web servers (EC2 instances) within Private Subnets for enhanced security.
	•	NAT Gateway: Enabled instances in the private subnets to access the Internet while keeping the instances themselves private.
	•	EC2 Instances: Hosted the WordPress website on EC2 instances located within Private Subnets for better security and performance.
	•	Application Load Balancer (ALB): Implemented an ALB to evenly distribute incoming web traffic to the EC2 instances within the Auto Scaling Group.
	•	Auto Scaling Group: Managed EC2 instances automatically to ensure availability, scalability, fault tolerance, and elasticity.
	•	Amazon RDS: Used Amazon RDS for the WordPress database to provide a managed, scalable, and high-performance database service.
	•	Amazon EFS: Employed Amazon EFS for shared file storage, enabling EC2 instances to access the same set of WordPress files.
	•	Certificate Manager: Secured communications with SSL/TLS certificates managed by AWS Certificate Manager.
	•	Amazon SNS: Configured SNS for notifications related to Auto Scaling Group activities to keep track of scaling events and system status.
	•	Route 53: Registered a domain name and set up a DNS record to route traffic to the Application Load Balancer.
	•	EC2 Instance Connect Endpoint: Implemented for secure access to instances within both public and private subnets.
