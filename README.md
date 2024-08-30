Host a WordPress Website on AWS

I recently completed a DevOps project where I hosted a WordPress website on AWS using various AWS resources to ensure high availability, scalability, and security. This repository contains the reference architecture diagram and scripts used to deploy the WordPress application on an EC2 instance.

Project Overview

The project involved setting up a robust and secure environment for hosting a WordPress website on AWS by configuring various AWS services, such as EC2, VPC, and RDS. Below is an overview of the architecture and the AWS resources used.

![2 _Host_a_WordPress_Website_on_AWS](https://github.com/user-attachments/assets/a0f55559-76b5-433d-82f9-efdd4cfd6db6)


Architecture Components

	1.	Virtual Private Cloud (VPC): Configured a VPC with both public and private subnets across two Availability Zones (AZs) to ensure high availability and fault tolerance.
	2.	Internet Gateway: Deployed an Internet Gateway to enable connectivity between instances within the VPC and the Internet.
	3.	Security Groups: Established Security Groups to act as network firewalls, controlling inbound and outbound traffic to instances.
	4.	Availability Zones: Utilized two Availability Zones to enhance system reliability and fault tolerance.
	5.	Subnets:
	•	Public Subnets: Used for infrastructure components such as the NAT Gateway and Application Load Balancer.
	•	Private Subnets: Positioned web servers (EC2 instances) within Private Subnets for enhanced security.
	6.	NAT Gateway: Enabled instances in the private subnets to access the Internet while keeping the instances themselves private.
	7.	EC2 Instances: Hosted the WordPress website on EC2 instances located within Private Subnets for better security and performance.
	8.	Application Load Balancer (ALB): Implemented an ALB to evenly distribute incoming web traffic to the EC2 instances within the Auto Scaling Group.
	9.	Auto Scaling Group: Managed EC2 instances automatically to ensure availability, scalability, fault tolerance, and elasticity.
	10.	Amazon RDS: Used Amazon RDS for the WordPress database to provide a managed, scalable, and high-performance database service.
	11.	Amazon EFS: Employed Amazon EFS for shared file storage, enabling EC2 instances to access the same set of WordPress files.
	12.	Certificate Manager: Secured communications with SSL/TLS certificates managed by AWS Certificate Manager.
	13.	Amazon SNS: Configured SNS for notifications related to Auto Scaling Group activities to keep track of scaling events and system status.
	14.	Route 53: Registered a domain name and set up a DNS record to route traffic to the Application Load Balancer.
	15.	EC2 Instance Connect Endpoint: Implemented for secure access to instances within both public and private subnets.
