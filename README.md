# 🔐 Password Management System in AWS (Passbolt)

A secure, open-source, cloud-hosted password manager built using **Passbolt** and deployed on **AWS EC2**, designed to ensure safe and encrypted storage and sharing of passwords. This project showcases a real-world implementation of cybersecurity best practices and cloud configuration.

---

## 📄 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Deployment Guide](#deployment-guide)
- [Security Measures](#security-measures)
- [Usage](#usage)
- [Limitations](#limitations)
- [Future Enhancements](#future-enhancements)

---

<a name="features"></a>
## ✅ Features

- Self-hosted password manager using **Passbolt CE (Community Edition)**
- Hosted on AWS EC2 with automatic HTTPS support via domain integration
- SSH-secured server access using key-based authentication
- Encrypted communication using **SSL/TLS**
- Two-Factor Authentication (2FA) via browser extension
- Strong passphrase enforcement for master credentials
- Admin dashboard for team and user management

---

<a name="tech-stack"></a>
## 🧰 Tech Stack

- **AWS EC2** – Cloud hosting for Passbolt server  
- **Ubuntu Linux** – Local VM for configuration and SSH  
- **Passbolt CE** – Open-source password management software  
- **TCP/IP, SSL/TLS, SSH** – Secure network communication protocols  
- **Chrome Extension** – For browser-based 2FA authentication  

---

<a name="prerequisites"></a>
## 🛠️ Prerequisites

- ✅ [AWS Account](https://aws.amazon.com/)
- ✅ Local Linux VM (Ubuntu recommended)
- ✅ Registered domain for HTTPS (optional but recommended)
- ✅ Google Chrome browser (for extension)
- ✅ Basic understanding of networking and Linux commands

---

<a name="deployment-guide"></a>
## 🚀 Deployment Guide

> 💡 _Note: AWS charges approx ₹0.52/hr for the EC2 instance used._

### 1. Deploy Passbolt via AWS Marketplace

- Go to Passbolt AWS Marketplace Page
- Select **Passbolt Community Edition**
- Choose the desired instance type and region
- Create a **Security Group** allowing HTTP (80), HTTPS (443), and SSH (22)
- Generate a **Key Pair** for SSH access

### 2. SSH Key Setup

- ssh-keygen

- Press Enter to confirm default path
- This creates your public/private key pair (usually in ~/.ssh/id_rsa.pub)

### 3. Launch & Access EC2 Instance

- Launch the EC2 instance from AWS Console
- Use the public IP address to SSH into the instance:

- ssh -i your-key.pem ubuntu@<public-ip>

### 4. Configure Passbolt

- Visit your EC2 instance’s public IP in a browser
- Begin the setup wizard
- Generate server GPG keys
- Optionally configure SMTP (for future email notifications)
- Set Admin User credentials

### 5. Install Chrome Extension & Finalize

- Download the Passbolt Chrome Extension
- Create a strong 15+ character passphrase
- Choose a Security Token for 2FA
- Login via the browser extension

---

<a name="security-measures"></a>
## 🔐 Security Measures

- All data encrypted in transit via SSL/TLS
- Server access restricted via SSH key-pairs
- Strong password and passphrase policies enforced
- Two-Factor Authentication (2FA) enabled using browser extension
- Hosted in a secure AWS environment following least privilege access model

---

<a name="usage"></a>
## 📦 Usage

- Login through Chrome using your Passphrase + 2FA token
- Store, manage, and share passwords securely
- Admin panel accessible for managing users and permissions

---

<a name="limitations"></a>
## ⚠️ Limitations

- SMTP not fully configured (limits email-based features)
- Currently no backup automation in place
- Domain HTTPS setup requires manual configuration (if desired)

---

<a name="future-enhancements"></a>
## 🌱 Future Enhancements

- Configure SMTP for email notifications (password resets, invites)
- Automate EC2 backup snapshots for disaster recovery
- Integrate domain with HTTPS using Let's Encrypt
- Dockerize deployment for portability
- Monitoring and logging via CloudWatch
