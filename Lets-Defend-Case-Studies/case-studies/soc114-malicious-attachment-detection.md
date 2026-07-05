# 🔍 SOC Case Study: Malicious Attachment Detection (SOC114)

**Platform:** LetsDefend

**Date:** July 5, 2026

**Severity:** HIGH

**Event ID:** 45

**Type:** Email Analysis / Malware Detection

**Action:** ✅ Contained & Resolved

---

## 📌 Incident Summary

**Alert Triggered:** SOC114 - Malicious Attachment Detected

**Source:** Email Gateway / Exchange Logs

**Verdict:** ✅ TRUE POSITIVE

### Initial Findings
An email containing a malicious attachment was detected by the email gateway. The attachment was flagged by antivirus and threat intelligence feeds. The email was delivered to the user's inbox before detection.

---

## 🛠️ Investigation Process

### Step 1: Alert Review
- **Alert Rule:** SOC114 triggers when an email attachment matches known malware signatures or suspicious file types
- **Initial Severity:** HIGH
- **Trigger:** Attachment hash matched multiple threat intelligence feeds
- **Email Status:** DELIVERED (before detection)

### Step 2: Email Analysis

**Email Details:**

| Field | Value |
|-------|-------|
| **Sender** | [attacker@malicious-domain.com] |
| **Recipient** | [employee@company.com] |
| **Subject** | [Invoice #2345 - Urgent Payment Required] |
| **Attachment** | [invoice_2345.exe] |
| **File Type** | .exe (Executable) |
| **File Size** | 245 KB |
| **Detection** | Antivirus flagged as Trojan.Generic.12345 |

### Step 3: Attachment Analysis

**File Hash:**

| Hash Type | Value |
|-----------|-------|
| **MD5** | [a1b2c3d4e5f6...] |
| **SHA-256** | [a1b2c3d4e5f6...] |

**VirusTotal Results:**
- **Detection Rate:** 35/70 vendors flagged as malicious
- **Common Name:** Trojan.Generic.12345
- **Type:** Remote Access Trojan (RAT)
- **Family:** [Emotet / Agent Tesla / etc.]

### Step 4: Threat Intelligence Correlation

| Tool | Finding |
|------|---------|
| **VirusTotal** | 35+ vendors flagged as malicious |
| **AbuseIPDB** | Sender IP associated with known phishing campaigns |
| **ANY.RUN** | Sandbox analysis confirmed malicious behavior |

### Step 5: User Context Analysis

| Field | Value |
|-------|-------|
| **User** | [Employee Name] |
| **Department** | [Finance / Sales / etc.] |
| **Previous Alerts** | None |
| **Likely Intent** | Unintentional (believed it was a legitimate invoice) |

### Step 6: Playbook Execution

1. ✅ Verify file hash against threat intelligence feeds
2. ✅ Confirm if attachment was opened or executed
3. ✅ Identify if any malware was installed
4. ✅ Isolate user endpoint if necessary
5. ✅ Reset credentials if compromised
6. ✅ Provide user training

---

## 🔑 Key Findings & Indicators of Compromise

### Indicators of Compromise

| IOC Type | Value |
|----------|-------|
| **File Hash (MD5)** | [a1b2c3d4e5f6...] |
| **File Hash (SHA-256)** | [a1b2c3d4e5f6...] |
| **File Name** | invoice_2345.exe |
| **Sender Domain** | malicious-domain.com |
| **Sender IP** | 185.x.x.x |
| **Malware Family** | [Trojan.Generic.12345] |

### Evidence Collected
- ✅ Email header analysis
- ✅ Attachment hash analysis
- ✅ VirusTotal report
- ✅ Sandbox analysis report

---

## 🚨 Root Cause & Impact

### Root Cause
- Attacker sent a phishing email impersonating a vendor
- Email attachment was disguised as an invoice
- Employee opened the attachment, believing it was legitimate
- Attachment executed malicious code

### Impact
- **Potential:** RAT installation → Data exfiltration → Lateral movement
- **Actual:** Endpoint isolated immediately
- **Business Impact:** Limited - contained quickly

---

## ✅ Resolution & Remediation

### Immediate Actions
1. 🔒 Isolated affected endpoint
2. 🗑️ Quarantined email from all mailboxes
3. 🔑 Reset user's credentials
4. 🛡️ Added file hash to blocklist
5. 🧹 Scanned endpoint for malware remnants

### Long-term Actions
1. 📚 User security awareness training
2. 🔄 Review email filtering rules
3. 📊 Update detection rules with new IOCs
4. 🔍 Conduct post-incident review

---

## 📊 MITRE ATT&CK Mapping

| Tactic | Technique | How It Was Detected |
|--------|-----------|---------------------|
| **Initial Access (TA0001)** | T1566.001 - Spearphishing Attachment | Email with malicious attachment delivered |
| **Execution (TA0002)** | T1204.002 - User Execution (Malicious File) | User opened the attachment |
| **Persistence (TA0003)** | T1547.001 - Boot or Logon Autostart Execution | Potential registry modification |
| **Command & Control (TA0011)** | T1071 - Application Layer Protocol | Potential outbound C2 traffic |

---

## 💡 Lessons Learned

| What Went Well | What Could Improve |
|----------------|-------------------|
| ✅ Quick detection by email gateway | ⚠️ Email was delivered before detection |
| ✅ Fast user endpoint isolation | ⚠️ User opened attachment |
| ✅ Proper threat intelligence correlation | ⚠️ Additional user training needed |
| ✅ Playbook execution | ⚠️ Review email filtering thresholds |

---

## 📎 Evidence

*Note: Evidence not included to maintain platform integrity*

---

**Analyst:** [Your Name]  
**Date:** July 5, 2026  
**Platform:** LetsDefend  
**LinkedIn:** linkedin.com/in/[your-profile]
