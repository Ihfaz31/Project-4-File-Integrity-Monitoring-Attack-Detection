# Project 4 – File Integrity Monitoring (FIM) using Wazuh

## Overview

This project demonstrates how a **Security Operations Center (SOC)** can detect unauthorized changes to important system files using **Wazuh File Integrity Monitoring (FIM)**.

File Integrity Monitoring checks critical files on a system and alerts security teams if a file is **modified, deleted, or newly created**. This helps detect **malware activity, insider threats, and system tampering**.

---

## Lab Environment

* **Wazuh Manager:** Ubuntu Virtual Machine
* **Monitoring Dashboard:** Wazuh Dashboard (Web Interface)
* **Virtualization Platform:** VirtualBox

The Wazuh Manager monitors system files and sends alerts to the dashboard when changes occur.

---

## How File Integrity Monitoring Works

1. Wazuh performs an **initial scan** of important directories and creates a **baseline** of file information.
2. When a file changes later, Wazuh compares the file with the baseline.
3. If differences are found, an **alert is generated in the Wazuh Dashboard**.

Directories monitored in this project include:

* `/etc`
* `/usr/bin`
* `/usr/sbin`
* `/bin`
* `/sbin`
* `/boot`

These folders contain important system files that attackers often target.

---

## Steps Performed

### 1. Verified Wazuh Manager

Checked that the Wazuh Manager service is running on Ubuntu.

### 2. Checked File Integrity Monitoring Configuration

Opened the Wazuh configuration file and confirmed that **syscheck (FIM)** was enabled.

### 3. Initial File Scan

Wazuh performed a baseline scan of monitored directories to record the original file states.

### 4. Simulated a File Modification

A monitored system file was modified to simulate unauthorized system changes.

Example:

```
sudo nano /etc/hosts
```

A small comment was added to simulate a change.

### 5. Alert Detection

Wazuh detected the file modification and generated a **File Integrity Monitoring alert** in the dashboard.

The alert shows:

* File path
* Type of modification
* Timestamp of the event
* Alert severity level

---

## Screenshots Collected

The following screenshots were captured for documentation:

1. Wazuh Manager running
2. Syscheck configuration in `ossec.conf`
3. File modification simulation
4. File Integrity Monitoring alert in Wazuh Dashboard
5. Dashboard showing multiple alerts

---

## Result

This project successfully demonstrated how **Wazuh detects unauthorized file changes** using File Integrity Monitoring.

Security teams can use this feature to quickly detect:

* Malware modifying system files
* Unauthorized configuration changes
* Suspicious activity on servers

---

## Skills Learned

* Security monitoring with **Wazuh SIEM**
* File Integrity Monitoring concepts
* Basic Linux security analysis
* SOC alert investigation

---

## Conclusion

File Integrity Monitoring is an essential security control used in many organizations. By implementing Wazuh FIM, system administrators and SOC analysts can detect suspicious file modifications and respond quickly to potential security threats.

File Integrity Monitoring is an essential security control used in many organizations. By implementing Wazuh FIM, system administrators and SOC analysts can detect suspicious file modifications and respond quickly to potential security threats.
