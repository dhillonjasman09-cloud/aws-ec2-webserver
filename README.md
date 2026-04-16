# AWS EC2 Web Server with Security Groups

## Overview
Deployed a live Apache web server on an AWS EC2 instance with 
properly configured security groups following least privilege principles.

## Architecture
- EC2 t3.micro instance (Amazon Linux 2023)
- Apache HTTP Server
- Security group with port 80 open to public, port 22 restricted to my IP only

## Steps Taken
1. Launched EC2 instance via AWS Console
2. Configured security group inbound rules:
   - SSH (port 22) locked to my IP address only
   - HTTP (port 80) open to 0.0.0.0/0
3. Connected via SSH from Windows PowerShell using .pem key pair
4. Installed and configured Apache web server
5. Deployed a custom HTML page

## Security Decisions
- Port 22 restricted to a single IP to prevent brute force attacks
- HTTPS not configured — would require SSL certificate via ACM 
  or Let's Encrypt with a custom domain
- Default security group detached to reduce attack surface

## Screenshots
**Live web server running in browser**
<img width="1094" height="1045" alt="image" src="https://github.com/user-attachments/assets/5d239574-12d1-4046-b185-6f852e7ce30a" />

**Security group inbound rules (least privilege)**
<img width="807" height="750" alt="image" src="https://github.com/user-attachments/assets/d4a42d90-f4a8-4707-a145-a594a6414d12" />

**Successful SSH connection from Windows PowerShell**
<img width="1112" height="357" alt="image" src="https://github.com/user-attachments/assets/41443541-758b-44c1-8d71-8908fa8739b2" />




## Technologies Used
- AWS EC2
- AWS Security Groups
- Apache HTTP Server
- Amazon Linux 2023
- SSH
