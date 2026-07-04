# Deloitte Cyber Job Simulation - Data Breach Investigation

## Project Overview
Completed Deloitte Australia's Cyber job simulation on Forage, investigating a real-world data breach scenario. Acted as a cyber security consultant to identify the source of a data leak at Daikibo Industrials.

## My Role
- Cyber Security Consultant at Deloitte Australia
- Investigated a data breach affecting industrial operations
- Analyzed web activity logs to identify suspicious activity

## Investigation Process
### 1. Log Analysis
Analyzed web_requests.log containing internal network traffic to Daikibo's telemetry dashboard.

### 2. Pattern Recognition
- **Normal Behavior:** Users request CSS, JS files before API calls
- **Suspicious Behavior:** Direct API calls with no preceding resource requests
- **Key Discovery:** Automated requests at exact hourly intervals (XX:00:48)

### 3. Threat Identification
- **Internal IP:** 192.168.0.101
- **User ID:** mdB7yD2dp1BFZPontHBQ1Z
- **Method:** Automated script scraping machine status data
- **Duration:** 24+ hours of continuous data exfiltration

## Key Findings
| Finding | Detail |
|---------|--------|
| **Attack Source** | Internal network (VPN access) |
| **Attack Method** | Automated hourly scraping |
| **Compromised Data** | Machine statuses across 4 factories |
| **Attacker ID** | mdB7yD2dp1BFZPontHBQ1Z |

## Recommendations
1. Block IP 192.168.0.101
2. Revoke user access (mdB7yD2dp1BFZPontHBQ1Z)
3. Implement API rate limiting
4. Review VPN access controls
5. Add authentication to all API endpoints
6. Monitor for similar patterns

## Screenshots
[View screenshots](./screenshots/)

## Skills Demonstrated
- 🔍 Log Analysis
- 🕵️ Threat Detection
- 📊 Pattern Recognition
- 📝 Incident Investigation
- 🔐 Security Recommendations
- 💼 Client Communication

## Certificate
[View Certificate](./certificate.pdf)

## Technologies
- Web Activity Logs
- Threat Analysis
- Security Investigation
- VPN/Network Security

---
**Author:** [Your Name]  
**Date:** [Date]  
**Platform:** Forage / Deloitte Australia
