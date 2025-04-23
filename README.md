# SPR530-Wazuh-SIEM-Project
Brute-force attack detection and response using Wazuh v4.5 in a SIEM lab environment. Includes comparative analysis of SIEM tools like Sentinel, QRadar, and Splunk. Final project for SPR530 at Seneca Polytechnic.
# Wazuh SIEM Threat Detection & Response – SPR530 Final Project

**Course:** SPR530 – Advanced Security Integration  
**Date:** April 2025  
**Institution:** Seneca Polytechnic

---

## 🧠 Overview
This project explores the use of **Wazuh v4.5**, an open-source Security Information and Event Management (SIEM) solution, to detect and respond to cyber threats in a simulated network. The demonstration involved simulating a **brute-force SSH attack** and using Wazuh to detect, alert, and attempt to automatically block the attack.

The original proposal was based on Microsoft Sentinel, but the project pivoted to Wazuh to enable full offline testing without licensing or cloud dependency.

---

## 🔍 Project Highlights

- **Simulated a Brute-Force SSH Attack** using Hydra from the agent VM  
- **Wazuh Agent** forwarded logs to the Wazuh Server for real-time analysis  
- **Alerts generated** using pre-configured rules (notably Rule ID 5760)  
- **Attempted automated mitigation** via Wazuh’s `firewalldrop` Active Response  
- **Comparative analysis** conducted between 6 SIEM tools: Splunk, QRadar, Sentinel, ArcSight, Sumo Logic, and Wazuh

---

## ⚙️ Technical Setup

| VM Name         | Role                   | IP Address      |
|----------------|------------------------|-----------------|
| Wazuh Server    | Manager + Dashboard    | 192.168.10.2    |
| Agent VM        | Wazuh Agent + Attacker | 192.168.10.3    |

- SSH service was enabled on the agent
- Brute-force attempts were run using Hydra
- Wazuh's Dashboard monitored failed logins in real-time
- Rule-based alerts were triggered during the attack
- Active response (`firewalldrop`) was configured but didn’t fully block the IP (likely config timing/permissions issue)

---

## 📚 Project Structure (Explained)
While no files are uploaded due to submission guidelines, the full project included:

- ✅ A detailed proposal outlining the research plan and tool selection process  
- ✅ A 25+ page report covering Wazuh architecture, comparative analysis, screenshots, configurations, and logs  
- ✅ A final PowerPoint presentation delivered live (10+ slides with figures and demo breakdown)  
- ✅ Screenshots included:  
  - Wazuh Dashboard detecting Rule ID 5760  
  - Active response config in `ossec.conf`  
  - Brute-force attempt logs  
  - `iptables` output confirming IP block attempts

---

## 🧠 Skills Demonstrated
- SIEM architecture & threat detection  
- Wazuh deployment and dashboard use  
- SSH brute-force simulation  
- Log correlation and alert rule tuning  
- Comparative security tool evaluation  
- Active response configuration

---

## ⚠️ Notes
While detection and alerting worked successfully, the Active Response (`firewalldrop`) block was not fully enforced. Logs show Wazuh attempted the action, but the attacker IP remained reachable — highlighting common tuning/debug challenges in real SIEM setups.

---

## ✅ Project Status
- ✔️ Wazuh setup and log monitoring validated  
- ✔️ Alerts triggered and dashboard populated  
- ⚠️ IP block via Active Response partially failed  
- ✔️ Research, demo, and presentation completed and submitted
