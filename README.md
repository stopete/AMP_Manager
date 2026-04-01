# ⚙️ AMP Manager (Apache Web Tool)

A Windows GUI utility to manage and monitor a local web development environment (Apache, MySQL, PHP).

---

### ▶️ Description

The **AMP Manager** provides a simple desktop interface to check the status of, start, stop, and restart Apache and MySQL services. It also provides quick access to their primary configuration files.

The application is designed to be robust, with extensive error handling at startup. It validates all application paths from an external `Settings.xml` file and will prevent itself from running if the configuration is critically flawed.

<img width="1238" height="651" alt="image" src="https://github.com/user-attachments/assets/d04b1062-9b31-4fa1-b588-b7a2fbee1b75" />


---

### ✨ Features

*   **Service Control:** Start, Stop, and Restart Apache and MySQL services with a single click.
*   **Configuration Access:** Instantly open `httpd.conf`, `httpd-vhosts.conf`, and `php.ini` in your default or preferred editor.
*   **Status Dashboard:** A comprehensive status check that validates paths, checks versions, and reports service status for Apache, PHP, MySQL, and OpenSSL.
*   **Robust Startup Validation:** The application will not run without a valid `Settings.xml` file, preventing unexpected errors.
*   **User-Friendly GUI:**
    *   The window always stays on top for easy access.
    *   A professional confirmation dialog prevents accidental closing.

---

### 📋 Requirements

*   Windows Operating System
*   PowerShell 5.1 or later
*   .NET Framework 4.5 or later
*   A correctly configured `Settings.xml` file in the same directory.

---

### 🛠️ Configuration

The most critical part of this tool is the **`Settings.xml`** file. It **must** be placed in the same directory as the executable. Create this file and populate it with the correct paths and service names for your local environment.

#### Example `Settings.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Settings>
    <PathSettings>
        <!-- Full path to the main executable for each application -->
        <Apachepath>C:\path\to\your\Apache24\bin\httpd.exe</Apachepath>
        <PHPpath>C:\path\to\your\php\php.exe</PHPpath>
        <MySQLpath>C:\path\to\your\MySQL\MySQL Server 8.0\bin\mysqld.exe</MySQLpath>
        <OpenSSLpath>C:\path\to\your\Apache24\bin\openssl.exe</OpenSSLpath>
    </PathSettings>
    <ServiceName>
        <!-- The exact name of the Windows Service for Apache and MySQL -->
        <ServiceApache>Apache2.4</ServiceApache>
        <ServiceMySQL>MySQL80</ServiceMySQL>
    </ServiceName>
</Settings>
```

**How to find your service names:**
1.  Open the Windows "Services" application.
2.  Find Apache and MySQL in the list.
3.  Right-click the service, go to **Properties**, and use the **"Service name"** (not the "Display name").

---

### 🚀 Usage

Simply run the compiled `ApacheOptions.exe` file.

1.  The application will perform a status check on startup. Check the console window for version information and path validation results.
2.  Select an action from the dropdown menu (e.g., "Stop http", "Open php.ini").
3.  Click the **"Go"** button to execute the action.
4.  Use the "Close" button or the "X" button in the title bar to exit the application.

---

### 🏗️ Building from Source

This project was built using **SAPIEN PowerShell Studio**.

1.  Open the `ApacheOptions.psf` project file in PowerShell Studio.
2.  Go to the **Build & Packager** settings.
3.  Ensure the **"Product Information"** (specifically "File Version" and "Product Version") is set to a valid format (e.g., `1.2.0.0`).
4.  Click **Build** to compile the `.exe`.

---

### 📜 License

This script is provided "as is" without warranty of any kind. Use at your own risk.
