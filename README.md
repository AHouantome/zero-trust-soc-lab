# 🔐 Zero Trust SOC Lab (pfSense + Splunk)

## 📌 Overview

This project demonstrates a **Zero Trust Network Architecture** combined with **SOC monitoring using Splunk SIEM** to detect, analyze, and block cyber attacks in a controlled lab environment.

The lab simulates real-world attacker behavior and showcases how security teams detect and respond to threats.

---

## 🎯 Objectives

* Simulate attacks using Kali Linux
* Enforce Zero Trust segmentation using pfSense
* Monitor logs using Splunk SIEM
* Detect and analyze malicious activity
* Visualize attacks using dashboards
* Document incident response

---

## 🧱 Lab Architecture

* **Firewall:** pfSense (Network segmentation & Zero Trust rules)
* **SIEM:** Splunk Enterprise (Log monitoring & detection)
* **Attacker:** Kali Linux
* **Target Network:** Windows / Internal LAN
* **DMZ Network:** 192.168.2.0/24

---

## ⚙️ Key Implementation

### 🔹 Network Segmentation (Zero Trust)

* LAN: `192.168.1.0/24`
* DMZ: `192.168.2.0/24`
* Traffic from DMZ → LAN is **blocked by default**

---

### 🔹 Firewall Rules (pfSense)

* Block DMZ → LAN
* Allow limited HTTP/HTTPS/DNS outbound
* Enforce least privilege access

---

### 🔹 Attack Simulation

**Tool:** Nmap (Kali Linux)

```
nmap -Pn -sS 192.168.1.0/24
```

Simulates reconnaissance activity (MITRE T1595).

---

### 🔹 Detection (Splunk SIEM)

```
index=main "UFW BLOCK"
| stats count as blocked_attempts by SRC
| sort -blocked_attempts
```

Identifies top attacking IPs and abnormal traffic patterns.

---

## 📸 Screenshots (Attack Story)

1. Attack initiated (Kali Linux)
2. Network segmentation (VMware)
3. DMZ created (pfSense interface)
4. Firewall rules enforced (Zero Trust)
5. Attack detected (pfSense logs)
6. Attack blocked (log evidence)
7. Summary visualization (pfSense dashboard)
8. Splunk detection search
9. Splunk dashboard (Top attacking IPs)

---

## 📊 SIEM Monitoring (Splunk)

* Real-time log ingestion
* Detection of blocked traffic
* Visualization of attack patterns
* Identification of malicious IPs

---

## 🧠 MITRE ATT&CK Mapping

* **T1595 – Active Scanning**
* **T1046 – Network Service Discovery**

---

## 🚨 Incident Summary

* **Attacker:** Kali Linux (192.168.2.x)
* **Target:** Internal LAN
* **Activity:** Network scanning
* **Detection:** Firewall logs + Splunk SIEM
* **Outcome:** All traffic successfully blocked

---

## 📄 Incident Report

See:
`Reports/incident-report.pdf`

---

## 🏁 Conclusion

This project demonstrates practical SOC skills:

* Network security (Zero Trust)
* Threat detection (Splunk SIEM)
* Log analysis
* Attack simulation
* Incident documentation

---

## 🚀 Skills Demonstrated

* SIEM (Splunk)
* Network Security (pfSense)
* Threat Detection & Analysis
* MITRE ATT&CK Mapping
* Incident Response
* Log Monitoring & Visualization
