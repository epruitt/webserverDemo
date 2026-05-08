# AWS VPC Infrastructure Setup (CDK)

This project demonstrates how to build a foundational AWS networking environment using the AWS Cloud Development Kit (CDK). It walks through creating a secure and scalable Virtual Private Cloud (VPC) along with the necessary components to host a publicly accessible web server.

## Overview

The setup begins with the creation of a VPC using the CIDR block `10.0.0.0/16`, providing a large private address space for resource deployment. Within this VPC, both public and private subnets are configured to separate internet-facing resources from internal services, improving security and architecture design.

To enable internet connectivity, an Internet Gateway is attached to the VPC, and route tables are configured with default settings using CDK to properly direct traffic between subnets and external networks.

Security is managed through AWS Security Groups, which act as virtual firewalls to control inbound and outbound traffic to resources within the VPC.

Finally, an EC2 instance is launched and configured with user data to automatically install and run a web server. This instance is deployed in a public subnet, allowing it to be accessed over the internet.

## Key Components

- **VPC**: Custom VPC with CIDR block `10.0.0.0/16`
- **Subnets**: Public and private subnet configuration
- **Internet Gateway**: Enables internet access for public resources
- **Route Tables**: Handles traffic routing within the VPC
- **Security Groups**: Controls access to resources
- **EC2 Instance**: Web server deployed with user data

## Purpose

This project provides a practical example of building a basic AWS network infrastructure using infrastructure as code (IaC) principles. It is ideal for learning core networking concepts and preparing for real-world cloud architecture scenarios.
