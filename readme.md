# **WiFi-Auto-Auth**
Tired of entering the same Wi-Fi credentials every time you join the network? So was I! At my institute, logging into Wi-Fi manually was a hassle, so I built this Auto WiFi Login Script to automate the process with the help of Python,SQLite and Crontab!

This script automatically logs into Wi-Fi networks using pre-saved credentials and now comes with SQLite integration to store login attempts and all payload parameters. It keeps track of all login activities, captures dynamic session parameters (a), and provides a user-friendly log display for debugging.

Ideal for schools, workplaces, or any location with recurring Wi-Fi logins, this script eliminates manual re-authentication and ensures effortless connectivity. It's fully customizable, works across different networks, and can even be automated on startup for a seamless experience.

### **For step-by-step setup instructions, please refer to [setup.md](https://github.com/01bps/WiFi-Auto-Auth/blob/main/setup.md)**

## **Logging Options**

The script includes a professional logging system with configurable verbosity levels and multiple output handlers:

### **Command Line Usage**

```bash
# Basic usage with default logging (INFO level)
python wifi_auto_login.py

# Debug mode with detailed diagnostic information
python wifi_auto_login.py --log-level DEBUG

# View recent login attempts only (no login attempt)
python wifi_auto_login.py --view-logs 10

# Custom log directory with file-only logging
python wifi_auto_login.py --log-dir ./custom_logs --no-console-logging --log-level INFO
```

### **Available Log Levels**
- `DEBUG`: Detailed diagnostic information for troubleshooting
- `INFO`: General application flow and login attempt details (default)
- `WARNING`: Warning messages for potential issues
- `ERROR`: Error conditions and failures
- `CRITICAL`: Critical errors that prevent operation

### **Environment Variables**
You can also configure logging using environment variables:
```bash
# Set log level and directory
LOG_LEVEL=DEBUG LOG_DIR=./prod_logs python wifi_auto_login.py

# Disable console logging for production
NO_CONSOLE_LOGGING=true python wifi_auto_login.py
```

### **Log Rotation**
- Automatic log rotation when files reach 10MB (configurable via `LOG_MAX_BYTES`)
- Keeps 5 backup files by default (configurable via `LOG_BACKUP_COUNT`)
- Separate formats for console (human-readable) and file (detailed debugging)

## **Security Notes**
- Credentials are securely stored in an SQLite database within your home directory.
- No sensitive data is transmitted except during the login request.
- Passwords are masked in logs for security.
- Login attempts are logged in SQLite, and old logs are automatically deleted after reboot


# **License:**
   This project is licensed under the [MIT License](LICENSE), which allows for free use, modification, and distribution.

🔧 **Need help?** Open an issue on GitHub!
