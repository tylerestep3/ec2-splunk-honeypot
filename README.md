# 🖥️ RDP Monitoring & Geo-Map Dashboard in Splunk

**Monitoring Windows RDP logins with real-time dashboards in Splunk Cloud** 🚀

---

## 🌐 Overview

This project demonstrates monitoring of **successful and failed RDP logins** on a Windows EC2 instance using Splunk Cloud. Key highlights:

- Single-value dashboards for login counts.  
- Geo-map visualization for failed login attempts.  
- Support for simulated attack data to validate dashboard functionality.  

---

## ✨ Key Features

- Captures Windows Security Event Logs:  
  - `4624` → Successful logins  
  - `4625` → Failed logins  
- Real-time dashboards with single-value counters.  
- Geo-map visualization of failed login attempts using IP geolocation.  

---

## 🛠️ Project Steps

### 1️⃣ Provision Windows EC2 Instance
- Deployed a Windows Server instance on AWS.  
- Enabled RDP access and configured security to allow traffic from anywhere.  
- Set up a test user account for login validation.  

<img width="1314" height="265" alt="image" src="https://github.com/user-attachments/assets/7a4605a5-121e-4d6d-ae8a-bd4e2359c239" />

---

### 2️⃣ Install & Configure Splunk Universal Forwarder
- Installed the **Splunk Universal Forwarder** on the EC2 instance.  
- Configured **inputs** to capture Security Event Logs (`4624` and `4625`).  
- Connected to **Splunk Cloud** using the provided credentials file.  
- Verified connectivity and successful log forwarding.  

---

### 3️⃣ Verify Logging in Splunk Cloud
- Logged into **Splunk Cloud** and opened the **Search & Reporting** app.  
- Ensured the EC2 instance is actively sending logs.  
- Example search to verify failed login events:
- Confirmed that both **failed (4625)** and **successful (4624)** login events appear.  
- Checked timestamps, source IPs, and account names to verify authenticity.  

<img width="1387" height="1143" alt="image" src="https://github.com/user-attachments/assets/ebd19340-4182-48d3-9b94-3645dfaa5684" />

---

### 4️⃣ Analyze & Validate via Dashboard
- Built **single-value panels** to track counts of successful and failed RDP logins.  
- Added a **geo-map visualization** for failed logins using:  
  - `iplocation` for geolocation  
  - `geom geo_countries` for mapping  
- Integrated simulated RDP attack logs to test dashboard behavior and map accuracy.  
- Used a **VPN** to generate failed logins from different countries to validate geo-mapping.  

<img width="1293" height="717" alt="image" src="https://github.com/user-attachments/assets/09c71f60-7f73-45db-8cc9-5f72ec194dd8" />

---

## 🧰 Technologies Used

- **Splunk Cloud** – SIEM and dashboard platform  
- **Splunk Universal Forwarder** – forward Windows Security logs  
- **Windows Server (EC2)** – RDP login testing environment  
- **AWS EC2** – cloud infrastructure  
- **PowerShell** – used to configure and troubleshoot the Splunk Universal Forwarder  

---

## 🚀 Usage

1. Deploy a Windows EC2 instance and enable RDP.  
2. Install **Splunk Universal Forwarder** and connect to Splunk Cloud.  
3. Configure Security Event Log inputs for `4624` and `4625`.  
4. Import the dashboard XML or manually build panels:  
   - Single-value counters for login counts  
   - Geo-map for failed login attempts  
5. Monitor login activity in real time using authentic and simulated (VPN-based) failed attempts.  


