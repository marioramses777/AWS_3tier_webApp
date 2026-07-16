# 3-Tier Web Application on AWS

## Short Description (for GitHub "About" section / LinkedIn)
A production-style 3-tier web application deployed on AWS, featuring a highly available architecture with auto-scaling, a private database layer, and secure bastion access. Built and demonstrated via console; infrastructure was torn down after testing to avoid ongoing AWS costs — see demo video below.

---

## 📐 Architecture

https://drive.google.com/file/d/1Cm_Yn-LQrO9Ia1X25DBNvH3uFIuQuNxF/view?usp=sharing

**Services used:**
- **VPC** — custom network with public and private subnets across multiple Availability Zones
- **EC2 + Auto Scaling Group (ASG)** — application servers, scaled automatically based on demand
- **Application Load Balancer (ALB)** — distributes traffic across EC2 instances in the ASG
- **RDS** — managed relational database in a private subnet, not publicly accessible
- **NAT Gateway** — allows private subnet instances to reach the internet (e.g., for updates) without being publicly exposed
- **Bastion Host** — single hardened entry point for SSH access into private instances

---

## 🎯 Design Decisions

- **Why ALB + ASG:** ensures high availability and automatic scaling under load, rather than a single point of failure on one EC2 instance.
- **Why private subnets for RDS:** the database should never be directly reachable from the internet — only from application servers inside the VPC.
- **Why a Bastion Host instead of exposing SSH publicly:** keeps a single, tightly controlled point of access into the private network, reducing attack surface.
- **Why NAT Gateway:** lets private instances download updates/patches without giving them public IPs.

---

## 🎥 Demo Video

Since I tore down the infrastructure after testing to avoid ongoing AWS costs, here's a walkthrough of the architecture and a live demo of the app running:

▶️ https://drive.google.com/file/d/1IPYAbPOzIIlEGdrGuwLGl_iNb6KwMguM/view?usp=drive_link

---

## 🛠️ How It Was Built

This version was deployed manually via the AWS Console to first validate the architecture end-to-end.

---

## 📌 Skills Demonstrated

`AWS` `VPC` `EC2` `Auto Scaling` `Application Load Balancer` `RDS` `NAT Gateway` `Bastion Host` `Networking & Security` `High Availability Architecture`

---

## 📬 Contact

Mario Medhat Ramses — https://www.linkedin.com/in/mario-ramses-376846179?utm_source=share_via&utm_content=profile&utm_medium=member_android — marioramses7777@gmail.com
