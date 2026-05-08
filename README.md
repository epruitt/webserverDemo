# 🌐 webserverDemo

> A foundational AWS networking environment built with the AWS Cloud Development Kit (CDK) — demonstrating how to create a secure, scalable VPC and deploy a publicly accessible web server using Infrastructure as Code.

---

## 📋 Overview

This project walks through provisioning core AWS networking components using **TypeScript CDK**, from a custom VPC to a live EC2-hosted web server. It's designed as a hands-on reference for learning cloud networking fundamentals and IaC best practices.

---

## 🏗️ Architecture

```
Internet
    │
    ▼
Internet Gateway
    │
    ▼
VPC (10.0.0.0/16)
 ┌──────────────────────────────┐
 │  Public Subnet               │
 │  ┌───────────────────────┐   │
 │  │  EC2 Web Server       │   │
 │  │  (User Data Script)   │   │
 │  └───────────────────────┘   │
 │  Security Group              │
 ├──────────────────────────────┤
 │  Private Subnet              │
 │  (Internal services)         │
 └──────────────────────────────┘
```

---

## 🔑 Key Components

| Component            | Description                                                   |
| -------------------- | ------------------------------------------------------------- |
| **VPC**              | Custom VPC with CIDR block `10.0.0.0/16`                      |
| **Public Subnet**    | Hosts internet-facing resources (EC2 web server)              |
| **Private Subnet**   | Isolated subnet for internal services                         |
| **Internet Gateway** | Enables outbound/inbound internet access for public resources |
| **Route Tables**     | Directs traffic between subnets and external networks         |
| **Security Groups**  | Virtual firewalls controlling inbound/outbound traffic        |
| **EC2 Instance**     | Web server auto-configured via user data script on launch     |

---

## 🛠️ Tech Stack

- **AWS CDK** (TypeScript)
- **AWS EC2**
- **AWS VPC / Networking**
- **Node.js / npm**
- **Jest** (testing)

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- [AWS CLI](https://aws.amazon.com/cli/) configured with valid credentials
- [AWS CDK CLI](https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html) installed globally

```bash
npm install -g aws-cdk
```

### Installation

```bash
# Clone the repository
git clone https://github.com/epruitt/webserverDemo.git
cd webserverDemo

# Install dependencies
npm install
```

### Deploy

```bash
# Bootstrap your AWS environment (first time only)
cdk bootstrap

# Preview the changes
cdk diff

# Deploy the stack
cdk deploy
```

### Destroy

```bash
cdk destroy
```

---

## 🧪 Testing

```bash
npm test
```

Tests are located in the `/test` directory and use the **Jest** framework.

---

## 📁 Project Structure

```
webserverDemo/
├── bin/                  # CDK app entry point
├── lib/                  # Stack definition (VPC, EC2, Security Groups)
├── test/                 # Unit tests
├── cdk.json              # CDK configuration
├── package.json          # Node.js dependencies
└── tsconfig.json         # TypeScript configuration
```

---

## 🎯 Purpose

This project serves as a practical, beginner-friendly example of building a basic AWS network infrastructure using **Infrastructure as Code (IaC)** principles. It is well-suited for:

- Learning core AWS networking concepts (VPC, subnets, routing, security groups)
- Getting hands-on experience with AWS CDK and TypeScript
- Preparing for AWS certifications or real-world cloud architecture roles

---

## 📄 License

This project is open source. See the repository for details.
