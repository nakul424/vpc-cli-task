# VPC – NAT Gateway Architecture

## 📌 Overview
This project demonstrates the setup of an AWS **VPC (Virtual Private Cloud)** with a **NAT Gateway** to enable secure outbound internet access for private subnet resources.  
It includes subnets, route tables, internet gateway, NAT gateway, and corresponding configuration.

---

## 📷 Architecture Diagram

Below is the VPC + NAT Gateway architecture diagram:

![VPC NAT Gateway](Vpc-Natgateway.png)

> **Note:** Replace `Vpc-Natgateway.png` with your actual uploaded image filename (PNG/JPG).  
> If your image is inside a folder like `images/`, update the path:  
> `![VPC NAT Gateway](images/Vpc-Natgateway.png)`

---

## 🧱 Components Included
- **VPC** (CIDR: customizable)
- **Public Subnet**
- **Private Subnet**
- **Internet Gateway (IGW)**
- **Elastic IP (EIP)**
- **NAT Gateway**
- **Route Tables**
- **EC2 Instances (optional)**

---


## 🔄 Traffic Flow Explanation
1. **Private subnet instance** sends outbound traffic (e.g., updates, package installs).
2. Traffic goes to the **private route table**, which routes `0.0.0.0/0` to the **NAT Gateway**.
3. The **NAT Gateway** uses its **Elastic IP** to access the internet.
4. Response traffic returns through the NAT Gateway → private subnet instance.
5. Instances in the private subnet **remain unreachable from the internet** (secure).

---

## 🚀 Purpose
This architecture is ideal for:![WhatsApp Image 2025-07-29 at 10 56 46 PM](https://github.com/user-attachments/assets/74138b34-2cc1-407c-97a4-86f9973818dc)
![WhatsApp Image 2025-08-04 at 9 36 33 AM](https://github.com/user-attachments/assets/a1769266-503b-413a-82df-f4a80456d439)
![git icon](https://github.com/user-attachments/assets/70150b2b-e8d8-40d5-ae73-380306a93b71)

- Secure backend servers
- Application servers needing outbound updates
- Database servers requiring internet patches
- Production workloads with public + private subnet separation

---


## 📁 Repository Structure
