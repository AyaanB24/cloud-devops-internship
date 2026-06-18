
---

# 🚀 AWS S3 + CloudFront Portfolio Hosting

## 📌 Overview

This project demonstrates how to deploy a **static portfolio website** using **Amazon S3 and CloudFront**, enabling a fast, secure, and globally accessible web application.

It follows a real-world **serverless deployment architecture** commonly used in modern DevOps workflows.

---

## 🏗️ Architecture

```text
Local Machine
      ↓
GitHub Repository
      ↓
Amazon S3 (Static Hosting)
      ↓
Amazon CloudFront (CDN + HTTPS)
      ↓
Global Users
```

---

## 🌐 Live Demo

👉 https://d2y6bvogsaqm3p.cloudfront.net/

---

## ⚙️ Tech Stack

| Layer        | Technology     |
| ------------ | -------------- |
| Frontend     | HTML5, CSS3    |
| Hosting      | AWS S3         |
| CDN          | AWS CloudFront |
| Version Ctrl | Git & GitHub   |

---

## 📁 Project Structure

```text
portfolio/
│
├── index.html
├── styles.css
│
└── assets/
    ├── Bucket Policy.png
    ├── CloudFront Dashboard.png
    ├── Live Portfolio.png
    └── S3 Bucket.png
```

---

## 🚀 Features

- Static portfolio website deployment
- Global CDN distribution using CloudFront
- HTTPS-enabled secure access
- Low latency via edge caching
- Serverless and cost-efficient architecture

---

## 🧠 AWS Concepts Applied

- Amazon S3 bucket creation
- Static website hosting configuration
- Bucket policy for public access
- CloudFront distribution setup
- CDN caching and edge locations
- HTTPS enforcement via CloudFront

---

## 🔧 Deployment Steps

### 1. Create S3 Bucket

- Create a globally unique bucket name
- Select region (e.g., ap-south-1)
- Enable static website hosting

---

### 2. Upload Files

- Upload:
  - `index.html`
  - `styles.css`
  - `assets/` folder

---

### 3. Configure Bucket Policy

Allow public read access for website files.

---

### 4. Create CloudFront Distribution

- Origin: S3 bucket
- Enable:
  - HTTPS redirect (HTTP → HTTPS)
  - Default caching behavior

---

### 5. Access Website

- Open CloudFront domain:

```text
https://d2y6bvogsaqm3p.cloudfront.net/
```

---

## 📸 Screenshots

Added the following screenshots in Screenshot folder:      

- S3 bucket configuration
- Static website hosting settings
- Bucket policy JSON
- CloudFront distribution dashboard
- Final live website output

---

## 💰 Cost Optimization

- Designed for AWS Free Tier usage
- Minimal cost for low traffic workloads
- CloudFront reduces direct S3 requests
- Bucket Key (SSE-KMS) can reduce encryption cost (optional optimization)

---

## 📌 Future Enhancements

- Custom domain setup using Route 53
- SSL certificate via AWS ACM
- CI/CD pipeline using GitHub Actions
- Automated deployment on push
- Cache invalidation strategy for updates

---

## 👨‍💻 Author

**Ayaan Bargir**
Full Stack Developer | DevOps Enthusiast

---

## 🎯 Key Learning Outcome

- Cloud-based static website hosting
- CDN architecture and caching strategy
- Secure content delivery using HTTPS
- Real-world AWS deployment workflow
- Basic DevOps pipeline understanding

---
