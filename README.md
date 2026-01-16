# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:
```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
Add this line (example):

html
Copy code
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
✅ This proof must be visible in your browser screenshot submission.

Quick Deploy (Ubuntu + Nginx)
1) Install Nginx
bash
Copy code
sudo apt update
sudo apt install -y nginx
sudo systemctl start nginx
sudo systemctl enable nginx
2) Download website code
bash
Copy code
git clone <THIS_REPO_URL>
cd dmi-portfolio-website/site
3) Copy to Nginx web root
bash
Copy code
sudo rm -rf /var/www/html/*
sudo cp -r ./* /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
sudo systemctl restart nginx
4) Verify
bash
Copy code
curl -I http://localhost
curl ifconfig.me
Open in browser:
http://<your-public-ip>

Troubleshooting
See: docs/TROUBLESHOOTING.md

Common issues:

Default Nginx page still showing → files not copied to /var/www/html

Permission denied → fix ownership and permissions

Nginx restart fails → run sudo nginx -t and check logs

License
MIT License.

yaml
Copy code

---

## Extra files you should add (small but professional)

### `docs/DEPLOY_NGINX_UBUNTU.md`
- Same steps as README but with screenshots placeholders + “what to capture”

### `docs/TROUBLESHOOTING.md`
Include:
- `sudo nginx -t`
- `systemctl status nginx`
- `tail -n 50 /var/log/nginx/error.log`
- `ss -tulpen`

---

## Repo description (GitHub “About”)
**Short:**  
Static portfolio website template for DMI Week 1 (Linux + Nginx deployment)

**Topics/tags:**  
`dmi` `devops` `linux` `nginx` `static-site` `html` `css` `portfolio`

---

If you want, I can also write:
- a **student-facing “Release Notes”** section (what to edit, where to edit)
- a **ZIP download link workflow** (GitHub Releases) so students can download without git (since git is not covered yet)