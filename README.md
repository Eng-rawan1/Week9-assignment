# Week 9 Assignment – Clarusway Website Deployment

---

## Overview

This project demonstrates deploying a static website using AWS infrastructure:

- *Amazon S3* for static asset hosting  
- *EC2 Auto Scaling Group with NGINX*  
- *Application Load Balancer (ALB)* for traffic distribution  

---

## ✅ Part 1: S3 Static Website

- Created bucket: rawan-clarusway-assets (Region: eu-north-1)  
- Enabled static website hosting  
- Uploaded: index.html, logo.png, sda.png  
- Added public-read bucket policy  

🔗 *S3 Website URL:*  
http://rawan-clarusway-assetsss.s3-website.eu-north-1.amazonaws.com/

---

## ✅ Part 2: EC2 Auto Scaling Group

- Created Launch Template with User Data (installs NGINX + serves HTML with hostname)  
- Used echo method instead of S3 copy to avoid IAM setup  
- Auto Scaling Group configured with:  
  - Min = 1  
  - Desired = 2  
  - Max = 3  

---

## ✅ Part 3: Application Load Balancer

- Internet-facing ALB on HTTP port 80  
- Target Group with health check on /  
- Verified round-robin response using hostname output  

🔗 *ALB URL:*  
http://clarusway-alb-699800848.eu-north-1.elb.amazonaws.com/

---

## 📸 Screenshots

- s3-site.png  
- s3-curl.png  
- ec2-running.png  
- asg-settings.png  
- alb-browser.png  
- alb-curl.png

---

## ✅ Cleanup

All AWS resources were deleted after successful deployment and testing.

---

## Notes

- HTML page was written via echo in User Data for simplicity  
- hostname was used to verify load balancing
