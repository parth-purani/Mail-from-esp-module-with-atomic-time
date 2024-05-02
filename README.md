# 📧 ESP32/ESP8266 Email Sending Script Overview

This script enables an ESP32 or ESP8266 microcontroller to connect to a WiFi network, configure email parameters, and send an email using SMTP (Simple Mail Transfer Protocol). It offers a comprehensive framework for network configuration, email composition, and managing SMTP operations with callbacks for detailed status updates.

## 🛠 Key Components and Functionality

### Libraries and Definitions

- **Conditional Inclusion**: Auto-detects and includes the correct WiFi library based on the microcontroller type (ESP32 vs. ESP8266).
- **SMTP Configuration**: Configures SMTP server settings (e.g., Gmail), including server addresses, ports, and user credentials.

### WiFi Connectivity

- **Setup**: Initiates and monitors the connection to a predefined WiFi network, reporting the connection status and displaying the device's IP address on successful connection.

### Email Configuration and Sending

- **SMTPSession**: Manages SMTP operations using an instance of `SMTPSession`.
- **Session_Config**: Stores all SMTP configuration details including server settings, login credentials, and NTP settings for accurate timestamping.
- **SMTP_Message**: Defines the email content, specifying sender and recipient details, and supports both HTML and plain text formats.

### SMTP Callback

- **smtpCallback**: Monitors and logs the email sending process, reporting status updates, outcomes, and detailed information on each email sent, such as timestamp, recipient, and subject.

## 🔄 Main Functions

- **setup()**: Performs initializations, connects to WiFi, configures SMTP settings, and sends an email. This function runs once at startup or reset.
- **loop()**: Remains empty in this script, as email operations are executed within the `setup()`.

## 📋 Detailed Process

1. **Initialize Serial and WiFi**: Starts with serial communication for debugging, then connects to the specified WiFi network.
2. **Email Setup**: Configures the SMTP session with necessary details, including authentication and connection parameters.
3. **Email Content**: Prepares the email content, opting for plain text to streamline the process.
4. **Send Email**: Attempts to connect to the SMTP server and sends the email, managing authentication status and handling any errors.
5. **Status Callback**: The `smtpCallback` function provides comprehensive logs of the email sending status, including both successes and failures.

## 🌐 Use Case

This script is particularly useful for IoT devices that need to send notifications or data via email, suitable for:
- Sending alerts based on sensor readings.
- Notifying users about system status changes.
- Automatically sending periodic reports from remote locations.

This script showcases a practical implementation of networking and SMTP functionalities on ESP platforms, emphasizing the integration of real-time data handling, network management, and communication.

---
Enhance your IoT projects with this robust email sending capability, ensuring your systems stay connected and communicative.
