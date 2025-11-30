# PHP Contact Form Setup Guide

## Problem
Live Server (port 5500) is a static file server and cannot execute PHP files. You need a PHP server to run the contact form.

## ⚠️ Current Status
PHP is not installed on your system. Choose one of the solutions below.

---

## Solution 1: Install PHP and Use Built-in Server (Recommended)

### Step 1: Install PHP

**Option A: Download PHP directly**
1. Go to https://windows.php.net/download/
2. Download the latest PHP 8.x Thread Safe version (ZIP file)
3. Extract to `C:\php`
4. Add PHP to your PATH:
   - Search "Environment Variables" in Windows
   - Edit "Path" variable
   - Add: `C:\php`

**Option B: Use XAMPP (Easier - includes Apache, MySQL, PHP)**
1. Download XAMPP from https://www.apachefriends.org/
2. Install it (includes PHP automatically)
3. PHP will be at: `C:\xampp\php\php.exe`

### Step 2: Start PHP Server

**If you installed PHP directly:**
1. Open PowerShell in your project folder
2. Run: `php -S localhost:8000`
3. Open: `http://localhost:8000/index.html`

**If you installed XAMPP:**
1. Copy your project to `C:\xampp\htdocs\Krishna Kumar Portfolio\`
2. Start Apache from XAMPP Control Panel
3. Open: `http://localhost/Krishna Kumar Portfolio/index.html`

**Or use the batch file:**
- Double-click `start-php-server.bat` (after PHP is installed)

Now your contact form will work!

## Solution 3: Use XAMPP/WAMP (Full Local Server)

1. **Download and install XAMPP** from https://www.apachefriends.org/
2. **Copy your project folder** to `C:\xampp\htdocs\`
3. **Start Apache** from XAMPP Control Panel
4. **Open browser:** `http://localhost/Krishna Kumar Portfolio/index.html`

## Solution 2: Use a Free Form Service (No PHP Setup Needed)

If you want to test immediately without installing PHP, use a form service:

### Option A: Formspree (Easiest)
1. Go to https://formspree.io/ and sign up (free)
2. Create a new form
3. Copy your form endpoint (e.g., `https://formspree.io/f/YOUR_FORM_ID`)
4. Update `index.html` line 286:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="post" class="php-email-form">
   ```
5. That's it! No PHP needed.

### Option B: EmailJS (JavaScript-based)
1. Sign up at https://www.emailjs.com/
2. Create an email service and template
3. Get your Service ID, Template ID, and Public Key
4. I can help you integrate this if needed.

**Note:** These services have free tiers but may have limitations. For production, PHP on a hosting server is recommended.

## Checking if PHP is Installed

Run this command in PowerShell:
```
php -v
```

If PHP is not installed, download it from: https://www.php.net/downloads.php

## Important Notes

- The PHP `mail()` function requires server configuration to actually send emails
- For local testing, emails won't actually send unless you configure a mail server
- For production, upload to a web hosting service that supports PHP

