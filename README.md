#Fishing App — Security Integration & Cloud Deployment Lab

![Next.js](https://img.shields.io/badge/Framework-Next.js-blue?logo=nextdotjs)
![Firebase](https://img.shields.io/badge/Backend-Firebase-orange?logo=firebase)
![AWS S3](https://img.shields.io/badge/Storage-AWS%20S3-yellow?logo=amazonaws)
![DigitalOcean](https://img.shields.io/badge/Hosting-DigitalOcean-blue?logo=digitalocean)
![Security](https://img.shields.io/badge/Focus-App%20Security-green)
![Status](https://img.shields.io/badge/Status-In%20Progress-lightgrey)

---

## Overview

**HookMyCharter** is a full-stack fishing charter booking platform that connects captains and customers through listings, map-based searches, and integrated bookings.  
This lab focuses on **auditing, securing, and deploying** the app from inherited source code to a production-ready cloud environment.

---

## Objective

To demonstrate the ability to:
- Audit a **Next.js + Node.js** web app for structural and security vulnerabilities.  
- Configure secure API routes for **Firestore** and **AWS S3**.  
- Run and debug the app locally via PowerShell and npm.  
- Prepare the project for **DigitalOcean** cloud deployment with production-grade security.

---

## Environment Setup

**Stack:**
- Node.js + npm  
- Next.js 13  
- Firebase Firestore  
- AWS S3  
- DigitalOcean Droplet (Ubuntu)  
- PowerShell for local testing  

**Local Setup:**
```bash
# Navigate to project folder
cd downloads/hookmycharter-main

# Install dependencies
npm install

# Start local development
npm run dev


---

Phase 1: Code Audit & API Hardening

Tasks Completed:

Verified file structure: package.json, /app/api/, /components/.

Restored missing .env configuration for secrets.

Corrected misconfigured S3 bucket variable in route.ts:

const bucket = "hookmycharter-images-2005";

Replaced deprecated Node APIs and added file input validation.


Security Improvements:

Implemented MIME type and size checks for uploaded files.

Sanitized filenames to prevent path traversal.

Added rate limiting (planned).

Scoped route access for authenticated users (in progress).



---

Phase 2: Cloud Integration

DigitalOcean Deployment Steps:

# Connect via SSH
ssh root@your_droplet_ip

# Clone repository
git clone https://github.com/dgutierrez-cyber/hookmycharter.git

# Install dependencies
npm install

# Set up environment variables
nano .env

Environment Variables:

FIREBASE_API_KEY=
FIREBASE_PROJECT_ID=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_BUCKET_NAME=hookmycharter-images-2005

Testing:

Verified /api/upload endpoint using Postman.

Confirmed Firestore read/write operations.

Tested S3 uploads from local image form.



---

Phase 3: Troubleshooting & Optimization

Issue	Resolution

ENOENT PowerShell path error	Corrected directory syntax with Set-Location
Invoke-WebRequest param error	Switched to proper curl.exe format
Missing AWS SDK modules	Installed @aws-sdk/client-s3
Build failures on Next.js 13	Adjusted TypeScript and app directory imports


Performance Upgrades:

Added Firestore indexes to reduce read latency.

Enabled Next.js static optimization for images.

Minified and cached build assets.



---

Next Steps

Implement JWT Authentication via Firebase Auth.

Add Role-Based Access Control (RBAC) for charter operators.

Configure NGINX reverse proxy + HTTPS on DigitalOcean.

Integrate monitoring/logging via PM2 + Cloudflare Analytics.



---

Screenshots / Evidence

Screenshot	Description

	Successful local npm run
	Verified file upload via API
	Firestore document structure
	App running on Droplet



---

Skills Demonstrated

Category	Skills

Web App Security	Input Validation, Secure Uploads, .env Secrets Management
Cloud Deployment	DigitalOcean Droplet Config, NGINX Setup
Development	Next.js 13, Node.js, Firebase Firestore, AWS SDK
Troubleshooting	PowerShell, Dependency Conflicts, npm Builds
Documentation	Markdown, GitHub Portfolio Formatting



---

📎 Repository

🔗 HookMyCharter Project

Author: Daniel Gutierrez
Date: November 2025
Role: Security-Focused Full Stack Developer
Focus: App Hardening & Cloud Deployment

