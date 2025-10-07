# Azure Virtual Machine Lab – Cost Optimization and Secure Access

## Overview
This lab simulates a scenario where 1,500 sensors deployed across the country send temperature and humidity data during daytime hours.  
The goal is to build a **cost-effective and secure virtual machine (VM)** in Azure that will later host code for processing this telemetry.

The Azure environment starts empty, and this lab walks through creating and configuring the VM with automation and security in mind.

---

## Objectives
- Deploy a virtual machine in Azure for future application hosting.  
- Configure **automatic shutdown** to reduce costs outside working hours.  
- Restrict **RDP access** to specific IP addresses for security.  
- Clean up resources to avoid unnecessary spend.

---

## Tasks

### **Task 1: Create a Virtual Machine**
- Create a new **Windows or Linux VM** in Azure (depending on requirements).  
- Use a **cost-effective size**, such as:
  - `Standard_B1s` or `Standard_B2s` (suitable for light workloads).  
- Use a **Standard HDD** for the OS disk instead of a Premium SSD to minimize costs.  
- Place the VM in an existing or new **resource group**.  
- Deploy the VM in a region close to the sensor network for low latency (optional).  

📸 *Screenshot Suggestion:* Deployment screen or “Virtual Machine Overview” page after creation.

---

### **Task 2: Configure Auto Shut-Down and Power-On**
- Navigate to the **Virtual Machine > Operations > Auto-shutdown** blade in the Azure portal.  
- Enable **Auto-shutdown** for **19:00 (7:00 PM)** local time.  
- (Optional) Configure a notification email before shutdown.  
- Note: The machine will be manually powered on by IT when needed during telemetry hours.

📸 *Screenshot Suggestion:* Auto-shutdown configuration screen showing the 7:00 PM setting.

---

### **Task 3: Configure Secure Access**
- Go to **Networking** under the VM settings.  
- Restrict inbound RDP (port 3389) access to **your public IP address only**.
  - Remove “Any” or 0.0.0.0/0 from allowed sources.  
  - Add a new rule:
    - **Source IP:** Your current public IP  
    - **Port:** 3389  
    - **Protocol:** TCP  
    - **Action:** Allow  
- This ensures only you can access the VM via RDP.

📸 *Screenshot Suggestion:* Network security group (NSG) rule showing restricted IP access.

---

### **Task 4: Clean Up Resources**
- Once all tasks are completed, delete all resources to avoid costs:
  - Virtual Machine  
  - Network Interface  
  - Public IP Address  
  - Network Security Group  
  - Disk  
  - Resource Group (if no longer needed)
  
📸 *Screenshot Suggestion:* Resource group deletion confirmation screen.

---

## Summary
This lab demonstrates how to:
- Deploy an Azure VM with cost-effective options.  
- Configure automation for off-hours shutdown to minimize costs.  
- Implement basic security measures by limiting RDP access.  
- Clean up resources in line with Azure cost management best practices.

---

## Files Included
- `architecture-diagram.drawio` – Visual representation of the Azure setup  
- `screenshots/` – Folder containing screenshots for each task  
- `README.md` – This file, describing the lab setup and steps
