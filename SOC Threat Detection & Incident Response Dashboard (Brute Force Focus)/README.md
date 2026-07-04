🔹 Title
# SOC Threat Detection & Incident Response Dashboard (Brute Force Focus)

**Description:**

This project simulates a real-world Security Operations Center (SOC) dashboard designed to detect, analyze, and respond to brute force attacks.

It provides visibility into security events through severity-based alert classification, attack timelines, attacker profiling, and an action-oriented triage system.

The dashboard enables analysts to quickly identify high-risk activities and take immediate response actions such as blocking malicious IPs and securing compromised accounts.

## 🚀 Key Features

- 🔴 Severity-based alert classification (Critical, High, Medium, Low)
- 📊 Attack timeline visualization
- 🌍 Geographical attack source tracking
- 🧠 Brute force detection using threshold logic
- 📋 Triage queue for incident investigation
- 🔽 Added drilldowns for interactiveness 
  
## 🧠 Detection Logic

Brute force attacks are detected using the following rule:

- More than 10 failed login attempts from a single IP within 1 minute → Critical Alert
- More than 5 failed attempts → High Alert

## 📸 Dashboard Preview
<img width="1365" height="767" alt="Screenshot 2026-07-04 172228" src="https://github.com/user-attachments/assets/3848ebb9-7a5b-4493-8ee4-ccb5456b4d57" />

## 🛠️ Tools & Technologies

- Splunk (SIEM)
- SPL (Search Processing Language)
- Data Visualization
- Cybersecurity Concepts (SOC Operations)

  ## 📚 Learning Outcomes

- Built a SOC-style monitoring dashboard
- Implemented brute force detection logic
- Simulated real-world incident triage workflow
- Designed actionable security insights for analysts

## 🎥 Video Walk-through Link: https://mega.nz/file/XlZSQSqD#jLJ3ooKFOBe3dGrKF0CCx5tVyR3ugLPpzaPByRwi8cc
