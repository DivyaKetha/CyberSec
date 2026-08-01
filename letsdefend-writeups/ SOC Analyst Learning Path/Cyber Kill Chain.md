<img width="806" height="323" alt="image" src="https://github.com/user-attachments/assets/f0dca879-c191-453d-b8a9-49b9aafeee8e" />


# Introduction to Cyber Kill Chain

**What is Lockheed Martin?**  
Established in 1995. Security and aerospace corporation. Researches, develops, designs, and produces advanced technological systems.

**What is Cyber Kill Chain?**  
Framework created by Lockheed Martin in 2011. Models cyberattacks in 7 sequential steps. If attacker fails at one step, next step cannot be executed.

**Significance of Cyber Kill Chain**  
Helps SOC analysts understand attack stages, identify where attacks occur, determine security flaws, and guide blue teams to strengthen defenses.

**Official Page:** https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html

---

**Questions**  
Q: How many steps does the Cyber Kill Chain model consist of?  
A: 7.

---

# Cyber Kill Chain Steps

**7 Steps:**
1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command & Control (C2)
7. Actions on Objectives

---

# Reconnaissance

First step of Cyber Kill Chain. Attacker gathers information about target system. More info = more attack surface.

**Two types:**
- **Passive Reconnaissance**: No direct interaction (e.g., web archives, open sources).
- **Active Reconnaissance**: Direct interaction (e.g., sending requests to web server to get version info).

**Attacker Actions:**
- Obtain server/software version info
- Gather publicly available data
- Collect employee emails
- Use social media for internal/personal employee info
- Detect internet-connected devices
- Find vulnerabilities on public servers
- Identify organization IP blocks
- Identify vendors the organization works with

**Defender Actions:**
- External pentests to find info disclosure
- Use Threat Intelligence for leak info
- Don't expose organizational documents online
- Monitor traffic with firewalls on internet-facing areas
- Apply updates immediately

---

**Questions**  
Q: What is the step in the Cyber Kill Chain model where the information gathering takes place?  
A: Reconnaissance.

---

**Scenario-Based Question**  
**Scenario:** APT38 targeted financial institution. Reconnaissance for several days on website. Found CVE-2019-0604 in Microsoft SharePoint. Exploited it. Deployed Powershell Empire backdoor.

Q: Based solely on this information, what is the number of distinct actions taken during the "Reconnaissance" phase? (Each sentence = separate action; enter numerical value)  
A: 3.  
*(Actions: 1. Conducted reconnaissance for several days on website. 2. Found CVE-2019-0604. 3. Identified SharePoint usage.)*

---

# Weaponization

Second step. Attacker uses recon info to prepare attack tools/scripts. Attack hasn't started yet; victim unaware.

**Attacker Actions:**
- Create malware
- Develop exploits
- Create phishing content (email templates, malicious documents)
- Identify best attack tool

**Defender Actions:**
- Check systems for known vulnerabilities
- Apply security updates ASAP
- Track known/new attack tools to detect when used

---

**Questions**  
**Scenario:** APT group targeted telecom. Collected emails from social media/open sources. Created phishing template. Created "Salaries.docx" with malicious macro. Sent phishing email. Victim viewed email and downloaded doc. Opened doc, macro ran. Ransomware installed via PowerShell.

Q: How many separate activities were performed in the "Weaponization" phase? (Each statement = separate action; enter numerical value)  
A: 2.  
*(Actions: 1. Created phishing email template. 2. Created malicious Word document with macro.)*

---

# Delivery

Third step. Attacker executes the cyber attack — first interaction with victim occurs. Malicious content transmitted via various methods.

**Attacker Methods:**
- Malicious URL or file attachment via email
- Malware via website
- Malicious URL or malware via social media
- Direct upload to target server
- Physical USB device

**Defender Actions:**
- Sandbox URLs in emails
- Scan attachments with antivirus
- Use email security solutions
- Train employees on security awareness
- Monitor server access and logs
- Use firewalls effectively
- Analyze suspicious activities
- Detect anomalies and find root cause

---

**Questions**  
**Scenario:** APT targeted defense sector. Detected IPs via Shodan/Zoomeye. Learned organization uses Windows. Embedded malware in putty.exe using Metasploit. Transferred malware to USB sticks. Left USB sticks on sidewalk. Employee plugged USB into company computer. Executed putty.exe. Attacker got reverse connection and ran remote commands. Added scheduled task for persistence. EDR flagged it. SOC analyst detected alert, took action, stopped attack.

Q: How many different actions were performed in the "Delivery" phase? (Each statement = separate action; enter numerical value)  
A: 2.  
*(Actions: 1. Transferred malware to USB sticks. 2. Left USB sticks on sidewalk.)*

---

# Exploitation

Fourth step. Attacker activates the malicious content delivered in previous step. Malware/exploit gets executed. If this fails, attack cannot proceed.

**Attacker Actions:**
- Execute exploit for hardware vulnerability
- Execute exploit for software/OS vulnerability
- Run malware

**Defender Actions:**
- Train employees on safe file handling
- Monitor system security operations for anomalies
- Track published vulnerabilities and write monitoring rules
- Apply security updates immediately
- Use EDR products
- Provide secure coding training
- Conduct regular pentests
- Perform automated vulnerability scanning
- Enforce least-privilege access

---

# Installation

Fifth step. Attacker establishes persistence on compromised system. Installs backdoor, dropper, or uses privilege escalation to maintain access. This is the Threat Hunting stage.

**Attacker Actions:**
- Install malware
- Place backdoor
- Install web shell on web server
- Add services, firewall rules, or scheduled tasks for persistence

**Defender Actions (Threat Hunting mindset — assume attacker is already inside):**
- Network Security Monitoring on all assets
- Use EDR to detect configuration changes
- Restrict and monitor access to critical files/paths
- Enforce least privilege for admin access
- Monitor running processes
- Allow only signed executables
- Detect anomalies and find root cause

---

**Questions**  
**Scenario:** EDR detected malware on a machine. SOC analyst determined malware had not been executed and no malicious activity occurred.

Q: In which step of the Cyber Kill Chain did the attacker fail, leading to detection? (Enter numerical value)  
A: 4. (Exploitation — malware was delivered but never executed.)

---

# Command and Control (C2)

Sixth step. Attacker sets up C2 server to send remote commands to compromised system. This is communication establishment, not objective execution.

**Attacker Actions:**
- Configure C2 server
- Enable victim device to communicate with C2

**Defender Actions:**
- Check systems for known C2 tools
- Block C2 IPs from Threat Intelligence via firewall
- Monitor network traffic for C2 communication

---

**Questions**  
**Scenario:** During network monitoring, analyst observed Windows machine connect to suspicious external IP. Deduced attacker could execute remote commands.

Q: What is the final Cyber Kill Chain step in which the attacker succeeded? (Enter numerical value)  
A: 6. (Command & Control — communication was established; actions on objectives not confirmed.)

---

# Actions on Objectives

Seventh and final step. Attacker executes the planned final actions. Activities depend on attacker's motivation.

**Attacker Actions:**
- Encrypt files with ransomware
- Exfiltrate critical data/documents
- Delete critical data to damage system
- Privilege escalation and lateral movement
- Collect user credentials
- Collect internal information
- Change/manipulate information

**Defender Actions:**
- Detect network anomalies
- Restrict and monitor outbound network access
- Restrict and monitor access to critical files/folders
- Monitor database access
- Use DLP products
- Detect unauthorized access

---

**Questions**  
Q: At what stage of the Cyber Kill Chain did the APT group "Cobalt Group" use the Sdelete tool to delete data? (Enter numerical value)  
A: 7. (Actions on Objectives — data destruction.)

---

Ready for the next module! Send it over.
