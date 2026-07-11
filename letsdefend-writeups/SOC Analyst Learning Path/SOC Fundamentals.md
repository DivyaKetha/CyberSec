# SOC Types and Roles
- A Security Operation Center (SOC) is an information security team that continuously monitors and analyzes security of an organization.
- Detect, analyze, respond using technology, people, and processes.

<br>

## Types of SOC Models
- **In-house SOC**: Cybersecurity team built within organization.
- **Virtual SOC**: No permanent facility; works remotely.
- **Co-Managed SOC**: Internal SOC working with external MSSP (Managed Security Service Provider).
- **Command SOC**: Oversees smaller SOCs across a large region - uses telecoms and defense agencies.

<br>

## People, Processes, and Technology
- People, processes, and technologies are required for SOC.
- **People**: Need team members who can adapt to new attacks and are willing to conduct research.
- **Processes**: Must align SOC structure with different types of security requirements (i.e., NIST).
- **Technology**: Team must have different products for many tasks (i.e., pentesting) to find best solution for organization.

<br>

## SOC Roles
- **SOC Analyst**: L1, L2, L3. Classifies alert, looks for cause, and provides advice on remediation.
- **Incident Responder**: Responsible for threat detection.
- **Threat Hunter**: Proactively seeks out and investigate potential threats and vulnerabilities.
- **Security Engineer**: Maintain security infrastructure of SIEM solutions and SOC products.
- **SOC Manager**: Budgeting, strategizing, managing staff, and coordinating operations.

<br>

# SOC Analyst and Their Responsibilities
- SOC Analyst plays an important role because they are the first to respond to a threat.
- Skills & Abilities:
  - **Operating Systems**: Need to know what is normal before determining what is abnormal.
  - **Network**: Will be dealing with lots of IPs and URLs.
  - **Malware Analysis**: Need to understand real purpose of malicious programs.
 
<br>

# SIEM and Analyst Relationship
- SIEM is a security solution - combining security information and event management.
- Features like filtering data and alerts are of most interest.
- Examples of SIEM solutions: IBM QRadar, ArcSight ESM, FortiSIEM, Splunk.
- "Take Ownership" means taking accountability of dealing with an alert.
- Would be useful to note false alerts and provide feedback to the team.

<br>

#### Q1: When you close an alert, which channel(tab on the monitoring page) can you access it from?
<pre>Closed Alerts</pre>

# Log Management
- Provides access to all logs in an environment (i.e., web logs, OS, firewall, proxy).
- Helps associate pieces of informations with each other (i.e., IP addresses).

<br>

**For the following questions you will need to click on Practice on LetsDefend then click on Log Management**

<br>

#### Q1: What source IP address entered the URL 'https://github.com/apache/flink/compare'?
<pre>172.16.17.54</pre>
Switch to **Basic**. Search using the provided URL to find the result related to the answer.

<br>

#### Q2: What is the type of log that has a destination port number of 52567 and a source IP address of 8.8.8.8?

Answer Format: logtype

<pre>DNS</pre>
Switch to **Pro**. Using the filters search for the destination port number. The result should show the log type.

<br>

# EDR - Endpoint Detection and Response
- Also known as Endpoint Threat Detection and Response (ETDR).
- Combines monitoring and data collection with rules-based automated capabilities.
- Examples: CarbonBlack, SentinelOne, FireEye HX.
- Containment involves isolating attacked machine from network.
  - Prevents lateral movement and increased exposure of other network assets.
- Indicators of Compromise (IoC) examples: IP address, file hash, process name, etc.
  - Can perform a quick search in EDR across all hosts and see if there's a match.  

<br>

#### Q1: What is the hostname of the device where the “nmap” file with a hash value of “83e0cfc95de1153d405e839e53d408f5” is executed?
<pre>EricProd</pre>
Given the hash value, use it to search for the device in EDR.

<br>

#### Q2: A "Ps1.hta" file was executed on a device with the hostname "Roberto". What is the complete CMD command?
<pre>C:/Windows/System32/mshta.exe C:/Users/roberto/Desktop/Ps1.hta</pre>
Search for **Roberto** go to **Terminal History** and you should see an entry that executed the Ps1.hta file.

<br>

# SOAR (Security Orchestration Automation and Response)
- SOAR enables security products and tools to work together.
- Examples: Splunk Phantom, IBM Resilient, Logsign, Demisto.
- Capabilities:
  - Threat Intelligence.
  - Case Management based Incident Response.
  - Vulnerability Management.
  - Endpoint Detection and Response.
  - Security Operations Automation.
  - Playbook Management.
- SOAR automates processes such as IP address reputation, hash querying, scanning files, etc.
- Playbooks ensure SOC team is on same page when performing their analysis.

<br>

# Threat Intelligence Feed
- Threat intelligence feeds are created for SOC teams to be aware of latest trends.
- Consists of data such as malware hashes, C2 domain/IP addresses, etc, provided by a third-party company.
- Can use free sources such as VirusTotal and Talos Intelligence.

<br>

#### Q1: What is the data source of the "e1def6e8ab4b5bcb650037df234e2973" hash on the threat intel page?
<pre>AbuseCH</pre>
Navigate to the Threat Intel section on LetsDefend. Search using the hash provided. One of columns show that AbuseCH is the data source associated with the hash.

<br>

# Common Mistakes made by SOC Analysts
- Over-reliance on VirusTotal results.
  - Accept only as a supporting tool.
  - Malicious software may be developed using an AV bypass technique. 
- Hasty Analysis of Malware in a Sandbox.
  - Malware may detect sandbox environment and not activate itself.
  - Malware may not become active 10 to 15 minutes after operation.
  - Analysis should be long as possible. 
- Inadequate Log Analysis.
  - Should also check if other devices are associated with the threat. 
- Overlooking VirusTotal Dates.
  - Should conduct a new search instead of looking at search cache.
