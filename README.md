<p align="center">
  <img src="https://wazuh.com/uploads/2021/02/wazuh-logo-blue.png" alt="Wazuh Logo" width="400"/>
</p>

# ☁️🛡️ Cloud-Based SIEM & XDR Deployment: Wazuh Home Lab 

![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kali-linux&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)
![Linode](https://img.shields.io/badge/Linode-00A95C?style=for-the-badge&logo=linode&logoColor=white)

## 🎯 Objective

The primary objective of this lab was to architect and deploy a centralized Security Information and Event Management (SIEM) and Extended Detection and Response (XDR) platform in the cloud. As a Cybersecurity & Red Team Enthusiast, I built this environment to simulate real-world enterprise defenses, specifically focusing on monitoring red team operations, analyzing file integrity, and mapping active offensive threats to the MITRE ATT&CK framework.

## 🏗️ Architecture & Infrastructure
* **Central Manager:** Wazuh Server hosted on Akamai Cloud (Linode) via an Ubuntu 22.04 instance (4GB RAM).
* **Target Endpoint:** Metasploitable 2 (Locally hosted on VirtualBox), communicating securely with the cloud manager over NAT.
* **Adversary Machine:** Kali Linux (Locally hosted) used to generate malicious traffic and test detection capabilities.

## ⚙️ Methodology
1. **Cloud Provisioning:** Deployed and secured the Ubuntu cloud infrastructure, retrieving deployment secrets and configuring firewall rules for agent communication over ports 1514 and 1515.
2. **Endpoint Configuration:** Installed the Wazuh Agent on the vulnerable Linux endpoint and established an encrypted telemetry streaming pipeline to the cloud manager.
3. **Offensive Simulation:** Executed active red team techniques against the endpoint to validate the SIEM's detection, alerting, and automated compliance mechanisms.

## ⚔️ Attack Simulations & Detections
To validate the defensive pipeline, I executed the following simulated attacks and monitored the resulting telemetry:

* **Reconnaissance (T1595):** Initiated aggressive Nmap service and port scans to trigger network anomaly alerts. 

* **Credential Access (T1110):** Executed an automated SSH brute-force attack using Hydra, successfully triggering multiple authentication failure alerts and observing the system's active response. 
  * *[ SH brute-force detection: proof]*
    <img width="2880" height="1436" alt="Brute Force Detect" src="https://github.com/user-attachments/assets/80b9c0ad-9f0a-4d8e-a0e5-0ff162fcba3d" />


## 💡 Key Takeaways
* **Cloud Operations:** Gained practical experience with cloud server provisioning, firewall management, and secure remote administration.
* **Red Team Telemetry:** Deepened my understanding of how noisy offensive tools (like Nmap and Hydra) generate distinct signatures and logs on the network layer.
* **Log Analysis:** Learned to navigate, filter, and query large datasets within a SIEM dashboard to isolate specific threat indicators and match them against known MITRE ATT&CK tactics.

---
*This lab project was built to bridge the gap between offensive operations and defensive monitoring, demonstrating practical skills in enterprise security architecture.*
