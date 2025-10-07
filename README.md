# Moodle LMS Deployment on AWS EC2

This project demonstrates the deployment and configuration of **Moodle Learning Management System (LMS)** on an **Ubuntu Server** hosted on **AWS EC2**. The project focuses on building a secure, scalable, and production-ready LMS environment suitable for hosting and managing online courses.

---

## 🧩 Technologies Used

* **AWS EC2** – Cloud hosting environment
* **Ubuntu Server 22.04 LTS** – Operating system
* **Apache / Nginx** – Web server
* **MySQL / MariaDB** – Database management system
* **PHP** – Server-side scripting language
* **Let’s Encrypt (Certbot)** – SSL/TLS certificate for HTTPS

---

## ⚙️ Project Overview

The project includes:

* Launching an EC2 instance and configuring security groups.
* Installing and configuring the **LAMP/LEMP stack**.
* Setting up Moodle with database and PHP extensions.
* Securing the site with SSL and firewall configurations.
* Ensuring server optimization and automation through cron jobs.

---

## 🚀 Installation Steps

Based on the guide: [Moodle on Ubuntu – Installation Guide](https://absprog.com/post/moodle-on-ubuntu)

1. Update and upgrade Ubuntu system packages.
2. Install Apache/Nginx, MySQL/MariaDB, and PHP with required extensions.
3. Create a Moodle database and assign privileges to a dedicated user.
4. Download Moodle, extract files, and configure file permissions.
5. Configure Apache virtual host for Moodle.
6. Run the Moodle setup wizard through the browser.
7. Install SSL certificate using **Certbot** and enable HTTPS.

---

## 🧱 Project Structure

Typical Moodle server directory layout after deployment:

```
/var/www/html/
├── moodle/                 # Moodle application core files
│   ├── admin/
│   ├── auth/
│   ├── course/
│   ├── lib/
│   └── config.php          # Main configuration file (database & paths)
│
/var/moodledata/            # Moodle data directory (outside web root)
│   ├── cache/
│   ├── filedir/
│   ├── sessions/
│   └── temp/
│
/etc/apache2/sites-available/
│   └── moodle.conf         # Apache virtual host configuration
```

**Important:**

* `/var/moodledata` must be writable by the web server user (`www-data`).
* `config.php` stores database and site path details.

---

## 🔧 Configuration Highlights

* Created `/var/moodledata` with proper permissions.
* Enabled Apache rewrite module and configured firewall rules (ports **80** and **443**).
* Scheduled Moodle cron jobs for background tasks.
* Optimized PHP and database settings for stable operation.

---

## 🧠 Challenges & Solutions

| Challenge                         | Solution                                                        |
| --------------------------------- | --------------------------------------------------------------- |
| Database connection errors        | Adjusted MySQL privileges and verified database character set   |
| Missing PHP extensions            | Installed required modules (`intl`, `xmlrpc`, `mbstring`, etc.) |
| Permission denied for Moodle data | Corrected ownership and directory permissions                   |
| SSL setup failure                 | Reissued Let’s Encrypt certificate and updated Apache vHost     |
| Cron job not running              | Configured Moodle cron under `www-data` user                    |

---

## ✅ Outcome

Successfully deployed a **production-ready Moodle LMS** on AWS EC2 with secure HTTPS access, reliable performance, and full administrative functionality for hosting online courses.

---

## 📚 Key Skills Demonstrated

* AWS EC2 Cloud Deployment
* Ubuntu Server Administration
* LAMP/LEMP Stack Configuration
* Moodle LMS Setup & Optimization
* SSL/TLS Security Management
* Database & File System Management

---

## 📄 License

This project is shared for educational and demonstration purposes.
Feel free to reuse or modify the setup with proper credit.
