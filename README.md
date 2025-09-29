# php-mysql-user-form

# User Data Collector (PHP + MySQL)

This project is a simple **User Data Collection Web Application** built using:
- **Apache Web Server**
- **PHP**
- **MySQL Database**

It allows users to submit personal information (name, age, country) and upload files.  
All the data is securely stored in the MySQL database.

---

## 🚀 Features
- User registration form with:
  - Name
  - Age
  - Country
  - File upload support
- Stores data in a MySQL database
- Uploads files to the server
- Database connection test page
- Easy deployment on Apache server

---

# Install Dependencies

On your web server (CentOS/RHEL example):

yum install httpd -y
dnf module -y enable php:8.1
dnf module -y install php:8.1/common
yum install mysql -y
yum install php-mysqli -y

3. Start Apache & MySQL
systemctl enable --now httpd
systemctl enable --now mysqld

# Configure Database

Login to MySQL and run:

CREATE DATABASE udc;
CREATE USER 'udc'@'%' IDENTIFIED BY '*******';
GRANT ALL PRIVILEGES ON udc.* TO 'udc'@'%';
USE udc;
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    country VARCHAR(255) NOT NULL
);

# Deploy PHP Files

Copy project files into your web server root:

cp -r * /var/www/html/

# 🌐 Usage

Open browser and visit:

http://<webserver-ip>/main.php


Fill in details and upload a file.

Submitted data will be stored in MySQL and file uploaded to /var/udc/uploads/.

