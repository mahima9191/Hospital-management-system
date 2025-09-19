# Hospital Management System 🏥

A comprehensive web-based Hospital Management System designed to streamline hospital operations, manage patient records, and improve healthcare service delivery.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Usage](#usage)
- [User Roles](#user-roles)
- [Screenshots](#screenshots)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [Testing](#testing)
- [Troubleshooting](#troubleshooting)
- [License](#license)
- [Contact](#contact)

## 🎯 Overview

The Hospital Management System is a web-based application designed to manage all hospital activities efficiently. It provides a centralized platform for managing patient information, appointments, medical records, billing, inventory, and staff management. The system aims to reduce paperwork, increase efficiency, and improve patient care quality.

### Key Objectives

- Digitize hospital operations and reduce manual paperwork
- Provide real-time access to patient information
- Streamline appointment scheduling and management
- Automate billing and payment processes
- Maintain comprehensive medical records
- Manage hospital inventory and supplies
- Generate detailed reports and analytics

## ✨ Features

### 🏥 Core Features

- **Patient Management**
  - Patient registration and profile management
  - Medical history tracking
  - Appointment scheduling
  - Discharge management
  - Patient search and filtering

- **Doctor Management**
  - Doctor profiles and specialization
  - Schedule management
  - Appointment tracking
  - Prescription management
  - Patient consultation history

- **Appointment System**
  - Online appointment booking
  - Appointment scheduling and rescheduling
  - Automatic notifications and reminders
  - Slot availability management
  - Queue management

- **Medical Records**
  - Electronic Health Records (EHR)
  - Prescription management
  - Lab test results
  - Medical imaging integration
  - Treatment history

- **Billing & Payments**
  - Automated bill generation
  - Payment processing
  - Insurance claim management
  - Financial reporting
  - Receipt generation

### 🔧 Administrative Features

- **Staff Management**
  - Employee registration and profiles
  - Role-based access control
  - Attendance tracking
  - Payroll management

- **Inventory Management**
  - Medicine stock tracking
  - Equipment management
  - Supplier management
  - Purchase order generation
  - Stock alerts and notifications

- **Reports & Analytics**
  - Patient statistics
  - Financial reports
  - Inventory reports
  - Doctor performance metrics
  - Hospital occupancy rates

## 💻 Technology Stack

### Frontend
- **HTML5** - Markup language for web pages
- **CSS3** - Styling and layout
- **JavaScript** - Client-side scripting
- **Bootstrap** - Responsive CSS framework
- **jQuery** - JavaScript library for DOM manipulation

### Backend
- **PHP** - Server-side scripting language
- **MySQL** - Relational database management system
- **Apache** - Web server

### Additional Tools
- **XAMPP/WAMP** - Local development environment
- **phpMyAdmin** - Database administration tool
- **Git** - Version control system

## 🖥️ System Requirements

### Minimum Requirements
- **Operating System**: Windows 7/8/10, macOS 10.12+, or Linux Ubuntu 16.04+
- **Web Server**: Apache 2.4+
- **PHP**: Version 7.4 or higher
- **MySQL**: Version 5.7 or higher
- **RAM**: 4GB minimum (8GB recommended)
- **Storage**: 2GB free disk space
- **Browser**: Chrome 70+, Firefox 65+, Safari 12+, Edge 79+

### Recommended Requirements
- **RAM**: 8GB or higher
- **Storage**: 10GB free disk space
- **Internet**: Stable broadband connection

## 🚀 Installation

### Prerequisites
1. Install XAMPP (recommended) or WAMP server
2. Ensure PHP and MySQL are properly configured
3. Install Git (optional, for cloning)

### Step 1: Clone or Download the Repository

```bash
# Clone the repository
git clone https://github.com/mahima9191/Hospital-management-system.git

# Navigate to the project directory
cd Hospital-management-system
```

Or download the ZIP file and extract it to your local server directory.

### Step 2: Setup Web Server

1. Copy the project folder to your web server directory:
   - **XAMPP**: `C:\xampp\htdocs\`
   - **WAMP**: `C:\wamp64\www\`
   - **MAMP**: `/Applications/MAMP/htdocs/`

2. Start Apache and MySQL services from your control panel

### Step 3: Configure Database Connection

1. Open the database configuration file (usually `config.php` or `connection.php`)
2. Update database credentials:

```php
<?php
$servername = "localhost";
$username = "root";          // Default XAMPP username
$password = "";              // Default XAMPP password (empty)
$dbname = "hospital_management";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
?>
```

## 🗃️ Database Setup

### Step 1: Create Database

1. Open phpMyAdmin in your browser: `http://localhost/phpmyadmin`
2. Create a new database named `hospital_management`
3. Import the database schema

### Step 2: Import SQL File

```sql
-- Navigate to the SQL tab in phpMyAdmin
-- Import the database file (hospital_management.sql)
-- Or run the following commands:

CREATE DATABASE hospital_management;
USE hospital_management;

-- Import your SQL file here
SOURCE path/to/hospital_management.sql;
```

### Step 3: Default Admin Credentials

After database setup, use these default credentials to access the admin panel:

- **Username**: `admin`
- **Password**: `admin123`

⚠️ **Important**: Change default credentials after first login for security.

## 🎮 Usage

### Accessing the System

1. Start your web server (Apache and MySQL)
2. Open your browser and navigate to: `http://localhost/Hospital-management-system`
3. You will see the login page

### First Time Setup

1. **Login as Admin**
   - Use default admin credentials
   - Change password immediately

2. **Configure System Settings**
   - Update hospital information
   - Set up user roles and permissions
   - Configure notification settings

3. **Add Initial Data**
   - Register doctors and staff
   - Set up departments
   - Configure appointment slots

## 👥 User Roles

### 🔴 Admin
- **Full System Access**
- Manage all users and roles
- View all reports and analytics
- System configuration and settings
- Database backup and maintenance

**Default Login**: admin / admin123

### 👨‍⚕️ Doctor
- **Patient Management**
- View and update patient records
- Manage appointments
- Write prescriptions
- Access medical history

**Sample Login**: doctor@hospital.com / doctor123

### 👩‍💼 Receptionist
- **Front Desk Operations**
- Patient registration
- Appointment scheduling
- Generate bills and receipts
- Manage patient check-in/out

**Sample Login**: receptionist@hospital.com / reception123

### 👤 Patient
- **Self-Service Portal**
- Book appointments online
- View medical records
- Download prescriptions
- Pay bills online

**Registration**: Patients can register themselves or be registered by staff

## 📸 Screenshots

### Dashboard
![Admin Dashboard](screenshots/admin-dashboard.png)
*Admin dashboard showing hospital statistics and quick actions*

### Patient Management
![Patient Management](screenshots/patient-management.png)
*Patient registration and management interface*

### Appointment Booking
![Appointment Booking](screenshots/appointment-booking.png)
*Online appointment booking system*

### Medical Records
![Medical Records](screenshots/medical-records.png)
*Electronic health records management*

## 📚 API Documentation

### Authentication Endpoints

```php
POST /api/login
{
    "username": "user@example.com",
    "password": "password123"
}
```

### Patient Endpoints

```php
GET /api/patients          # Get all patients
GET /api/patients/{id}     # Get specific patient
POST /api/patients         # Create new patient
PUT /api/patients/{id}     # Update patient
DELETE /api/patients/{id}  # Delete patient
```

### Appointment Endpoints

```php
GET /api/appointments               # Get all appointments
POST /api/appointments              # Book new appointment
PUT /api/appointments/{id}/status   # Update appointment status
```

## 🤝 Contributing

We welcome contributions to improve the Hospital Management System! Here's how you can contribute:

### Getting Started

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Make your changes
4. Test thoroughly
5. Commit your changes: `git commit -m 'Add new feature'`
6. Push to the branch: `git push origin feature/new-feature`
7. Submit a pull request

### Contribution Guidelines

- Follow PSR-4 coding standards for PHP
- Write clear, commented code
- Test all new features
- Update documentation as needed
- Maintain backwards compatibility

### Reporting Issues

If you find a bug or have a feature request:

1. Check existing issues first
2. Create a detailed issue report
3. Include steps to reproduce (for bugs)
4. Provide system information

## 🧪 Testing

### Manual Testing

1. **Patient Registration Flow**
   - Register new patient
   - Verify data storage
   - Test validation rules

2. **Appointment Booking**
   - Book appointments
   - Test slot conflicts
   - Verify notifications

3. **Billing System**
   - Generate bills
   - Process payments
   - Verify calculations

### Database Testing

```sql
-- Test patient data integrity
SELECT * FROM patients WHERE phone_number IS NULL;

-- Test appointment conflicts
SELECT * FROM appointments 
WHERE doctor_id = 1 
AND appointment_date = '2024-01-15' 
AND time_slot = '10:00:00';
```

## 🔧 Troubleshooting

### Common Issues

#### 1. Database Connection Error
```
Error: Connection failed: Access denied for user 'root'@'localhost'
```
**Solution**: 
- Check MySQL credentials in config.php
- Ensure MySQL service is running
- Verify database exists

#### 2. Page Not Loading
```
Error: 404 - Page not found
```
**Solution**:
- Check Apache service status
- Verify file paths
- Check .htaccess configuration

#### 3. Login Issues
```
Error: Invalid username or password
```
**Solution**:
- Verify database has admin user
- Check password encryption method
- Reset admin credentials if needed

#### 4. PHP Errors
```
Error: Call to undefined function mysqli_connect()
```
**Solution**:
- Enable mysqli extension in php.ini
- Restart Apache server
- Check PHP version compatibility

### Performance Optimization

1. **Database Optimization**
   - Add indexes to frequently queried columns
   - Optimize slow queries
   - Regular database maintenance

2. **Server Configuration**
   - Increase PHP memory limit if needed
   - Optimize Apache configuration
   - Enable caching mechanisms

### Backup and Recovery

#### Creating Backup
```bash
# Database backup
mysqldump -u root -p hospital_management > backup.sql

# File backup
tar -czf hospital_backup.tar.gz /path/to/hospital-management-system
```

#### Restoring Backup
```bash
# Restore database
mysql -u root -p hospital_management < backup.sql

# Restore files
tar -xzf hospital_backup.tar.gz
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Hospital Management System

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 📞 Contact

### Project Maintainer
- **Name**: Mahima
- **GitHub**: [@mahima9191](https://github.com/mahima9191)
- **Email**: [Add your email here]

### Support
- **Issues**: [GitHub Issues](https://github.com/mahima9191/Hospital-management-system/issues)
- **Discussions**: [GitHub Discussions](https://github.com/mahima9191/Hospital-management-system/discussions)

### Acknowledgments

- Thanks to all contributors who have helped improve this project
- Special thanks to the healthcare professionals who provided valuable feedback
- Built with ❤️ for better healthcare management

---

## 🚀 Quick Start Guide

For those who want to get started quickly:

1. **Download** or clone the repository
2. **Extract** to your web server directory (htdocs/www)
3. **Import** the database file through phpMyAdmin
4. **Configure** database connection in config.php
5. **Access** the system at `http://localhost/Hospital-management-system`
6. **Login** with default admin credentials
7. **Start** managing your hospital!

---

*⭐ If you find this project helpful, please consider giving it a star on GitHub!*

*🐛 Found a bug? Please report it in the issues section.*

*💡 Have an idea for improvement? We'd love to hear it!*
