
# HNG DevOps Stage 0

## Project Overview
This project involves provisioning and configuring a Linux server on AWS EC2 to serve a static HTML page and a JSON API endpoint over HTTPS.

## Server Details
- **Cloud Provider:** AWS EC2
- **Instance Type:** t3.micro
- **OS:** Ubuntu 24.04 LTS
- **Domain:** https://akins-stage0.duckdns.org

## What Was Done

### 1. Server Setup
- Provisioned Ubuntu EC2 instance on AWS
- Created non-root user `hngdevops` with sudo privileges
- Disabled root SSH login
- Disabled password authentication (key-based only)

### 2. Firewall (UFW)
- Allowed only ports 22, 80, and 443
- All other ports blocked

### 3. Nginx Configuration
- Installed and configured Nginx
- `GET /` returns HTML page with username visible
- `GET /api` returns JSON:
```json
{
  "message": "HNG14 Stage 1",
  "track": "DevOps",
  "username": "akin_hng"
}
```

### 4. SSL
- Obtained Let's Encrypt SSL certificate via Certbot
- HTTP automatically redirects to HTTPS with 301

## Live Endpoints
- **Homepage:** https://akins-stage0.duckdns.org
- **API:** https://akins-stage0.duckdns.org/api
## Evidence / Screenshots

### Validation Checks (HTTPS 200 OK, UFW, Nginx)
<img width="1056" height="254" alt="Screen Shot 2026-05-01 at 05 07 09" src="https://github.com/user-attachments/assets/649a134c-a1d7-4d81-8e6f-42a412731d55" />

<img width="1056" height="254" alt="Validation" src="https://github.com/user-attachments/assets/7fb5b841-389...
<img width="620" height="439" alt="Screen Shot 2026-05-01 at 05 09 32" src="https://github.com/user-attachments/assets/1fea0176-0b51-4c95-b1a0-7b1b47d77649" />

### API & curl results
<img width="620" height="439" alt="API Response" src="https://github.com/user-attachments/assets/06ca2d9e-e...
