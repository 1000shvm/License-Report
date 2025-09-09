# Password Expiration Notification using Power Automate

## 📄 Overview
This repository contains a document titled **"Lisence Report 1 (1).docx"**, which provides step-by-step guidance on creating a Power Automate flow to send password expiration notifications and monitor Microsoft 365 license usage.

The flow leverages **Microsoft Graph API** to retrieve license information and uses **Power Automate Premium features** for automation.

---

## 🚀 Purpose
The main objective of this document is to:
- Automate notifications for account password expiration.
- Monitor Microsoft 365 license usage (focus on E5 licenses).
- Alert administrators when available licenses drop below a threshold (e.g., 100).

---

## 🛠️ Implementation Steps
The document explains the process in two main parts:

### 1. App Registration in Azure AD
- Create an **App Registration** in Azure AD.
- Grant appropriate **Graph API permissions** (`Organization.Read.All`).
- Generate a **Client Secret** for authentication.
- Collect necessary details:  
  - Application (client) ID  
  - Directory (tenant) ID  

### 2. Creating the Power Automate Flow
- Use a **Scheduled Flow** (daily/weekly).
- Configure an **HTTP GET request** to:  
  [https://graph.microsoft.com/v1.0/subscribedSkus](https://graph.microsoft.com/v1.0/subscribedSkus)
- Parse the JSON response.
- Filter licenses (ignore those with `0` active, focus on E5).
- Initialize variables and calculate free licenses.
- Apply a **condition**: if free licenses ≤ 100 → send an **email notification**.

---

## 📦 Contents
- `Lisence Report 1 (1).docx` → Detailed guide with step-by-step instructions, screenshots, and configurations.

---

## ✅ Prerequisites
- Azure AD with admin access.
- Power Automate Premium license.
- Microsoft Graph API permissions.
- Basic knowledge of Power Automate flows.

---

## 📧 Notifications
The final flow ensures:
- Admins are automatically alerted when available licenses are running low.
- Proactive license management and password expiration tracking.

---

## 🔗 References
- [Microsoft Graph API Documentation](https://learn.microsoft.com/en-us/graph/overview)  
- [Power Automate Documentation](https://learn.microsoft.com/en-us/power-automate/)

---

## 📝 Author
Prepared as part of an automation guide for license and password expiration monitoring.
