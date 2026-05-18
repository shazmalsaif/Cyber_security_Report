##  Manual Setup on LAMP Stack (Ubuntu/Debian)

### ✅ Prerequisites

```bash
sudo apt update
sudo apt install apache2 mysql-server php php-mysqli git
```

### 📥 Setup DVWA

```bash
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git
cd DVWA
sudo cp config/config.inc.php.dist config/config.inc.php
sudo chown -R www-data:www-data /var/www/html/DVWA
```

### 🛠️ Configure Database

1. Edit `config.inc.php` and set:

   ```php
   $_DVWA['db_password'] = 'your_mysql_root_password';
   ```
2. Start MySQL and Apache:

   ```bash
   sudo systemctl start apache2
   sudo systemctl start mysql
   ```

### 🌐 Access DVWA

Open:

```
http://localhost/DVWA/setup.php
```

---

## 🔐 Optional Hardening

* Use a virtual machine (e.g., Kali,Ubuntu VM)
* Use host-only networking or NAT for isolation
* Reset DVWA frequently when testing destructive exploits

---

## 🧪 Post-Installation Checklist

* [ ] Apache and MySQL are running
* [ ] DVWA loads at `localhost`
* [ ] Database setup completed
* [ ] Security level can be adjusted
* [ ] You’re testing in a **safe, isolated environment**

---

## 🙋 Troubleshooting

* **403 Forbidden?** Check file permissions.
* **No DB connection?** Ensure MySQL is running and the credentials in `config.inc.php` are correct.
* **CSRF token errors?** Clear cookies and refresh the page.

---
