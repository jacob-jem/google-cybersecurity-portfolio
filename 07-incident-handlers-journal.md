# Incident Handler's Journal

## Entry 1

**Date:** September 14, 2026

### Description

An organized hacking group used phishing emails to launch a ransomware attack on a small U.S. health care clinic, locking staff out of critical patient data and bringing business operations to a halt. I am tasked with analyzing this security incident.

This entry pertains to both the Detection and Analysis and the Containment, Eradication, and Recovery phases of the NIST Incident Response Lifecycle because the scenario describes how the company discovered the incident and what it then did to address it.

### Tool(s) used

N/A

### The 5 W's

**Who caused the incident?**

An organized hacking group with a track record of targeting healthcare and transportation organizations.

**What happened?**

The attackers sent targeted phishing emails to several of the clinic's employees. Each email carried a malicious attachment that, once downloaded, infected the employee's computer with malware and gave the attackers a way into the network. From there, they deployed ransomware that encrypted the clinic's critical files.

**When did the incident occur?**

Tuesday at around 9:00 a.m.

**Where did the incident happen?**

At a small primary-care health clinic in the U.S.

**Why did the incident happen?**

The incident occurred because at least one of the targeted employees opened a phishing email and downloaded its malicious attachment.

The attackers likely conducted the attack for financial gain, as they followed up the ransomware with a ransom note on the employees' screens demanding a large payment for the decryption key.

### Additional notes

- Did the company have regular company-wide cybersecurity training to teach employees how to detect and handle phishing emails?
- Did the company have technical controls in place, like proper email filters, to minimize the chance of phishing emails reaching employees?
- Did the employee(s) accidentally or purposefully open the phishing email(s) and download the malicious attachment(s)?
- Did the company have a proper incident response plan to deal with a ransomware incident? What is the ideal way for the company to respond to the attackers' demands?
- How can the company improve its overall security posture to prevent a security incident like this from happening again?

## Entry 2

**Date:** September 16, 2026

### Description

I am tasked with investigating a user's traffic to a website by analyzing a packet capture of their connection to that site.

This entry pertains to the Detection and Analysis phase of the NIST Incident Response Lifecycle because it involved directly analyzing network packets to understand a specific user's web traffic.

### Tool(s) used

I used Wireshark, a network protocol analyzer (packet sniffer) that can capture network traffic and let you inspect it packet by packet.

### The 5 W's

**Who caused the incident?**

N/A. No incident was detected.

**What happened?**

No incident occurred. This entry was an assigned task to analyze a user's website traffic in Wireshark.

**When did the incident occur?**

N/A. No incident was detected.

**Where did the incident happen?**

N/A. No incident was detected.

**Why did the incident happen?**

N/A. This entry was an assigned task rather than an incident.

### Additional notes

Wireshark is a very intuitive and powerful tool for inspecting and analyzing network traffic.

## Entry 3

**Date:** September 16, 2026

### Description

I am tasked with monitoring live network traffic, saving a sample of web traffic to a packet capture (pcap) file, and then filtering that file to examine specific packet details.

This entry pertains to the Detection and Analysis phase of the NIST Incident Response Lifecycle because it involved capturing and directly analyzing network packets to understand what kind of traffic was moving across the network.

### Tool(s) used

I used tcpdump, a command-line network protocol analyzer that can capture traffic on a chosen network interface, save it to a pcap file, and read it back for analysis.

### The 5 W's

**Who caused the incident?**

N/A. No incident was detected.

**What happened?**

No incident occurred. This entry was an assigned task to capture and analyze network traffic with tcpdump.

**When did the incident occur?**

N/A. No incident was detected.

**Where did the incident happen?**

N/A. No incident was detected.

**Why did the incident happen?**

N/A. This entry was an assigned task rather than an incident.

### Additional notes

tcpdump is a lightweight but powerful tool for capturing and analyzing network traffic right from the command line.

## Entry 4

**Date:** September 21, 2026

### Description

An employee at a financial services company received a phishing email with a password-protected file attached. When they downloaded the file and opened it using the password included in the email, a malicious payload ran on their computer. I am tasked with using VirusTotal to learn more about the payload and the indicators of compromise (IoCs) tied to it, then working through the company's phishing playbook to decide whether to escalate or close the alert.

This entry pertains to the Detection and Analysis phase of the NIST Incident Response Lifecycle because it involved using VirusTotal to better understand the nature of the malicious payload in the phishing email, then following the company's phishing playbook to properly escalate the alert.

### Tool(s) used

I used VirusTotal, a threat intelligence service that checks a file (or its hash), URL, domain, or IP address against more than 70 antivirus scanners and URL/domain blocklisting services at once to determine whether it's malicious and, if so, show related IoCs.

### The 5 W's

**Who caused the incident?**

The malicious threat actor(s) who sent the phishing email to the employee.

**What happened?**

The employee got an email with a password-protected spreadsheet attached, along with the password needed to open it. Once the employee downloaded the spreadsheet and opened it with that password, a malicious payload ran on their computer.

**When did the incident occur?**

Wednesday, July 20, 2022, from 1:11 p.m. to 1:20 p.m.

**Where did the incident happen?**

At a financial services company.

**Why did the incident happen?**

The incident occurred because the employee downloaded and opened the malicious file attachment in the phishing email.

### Additional notes

After looking up the file's SHA256 hash on VirusTotal, I confirmed it was malicious for the following reasons:

- 51 out of 70 security vendors flagged it as malicious.
- It has a very negative community score of -294, meaning the VirusTotal community has strongly voted it as malicious.
- The security vendors' analysis section is full of vendors identifying it as a known malware family called Flagpro.

I also noticed that the phishing playbook doesn't account for phishing emails that contain no malicious link or attachment but instead include a phone number for the target to call, so the attacker can manipulate them over the phone into revealing sensitive information. Under the current playbook, the level-one SOC analyst investigating the alert ticket for an email like that would simply close it.

## Entry 5

**Date:** September 24, 2026

### Description

Before I joined a mid-sized retail company, an attacker accessed and stole customers' personally identifiable information (PII) and financial information, affecting about 50,000 customer records and costing the company an estimated $100,000 in direct costs and potential lost revenue. My task is to go through the incident's final report.

This entry pertains to the Post-Incident Activity phase of the NIST Incident Response Lifecycle because it involves reviewing the final report that was written after the incident was resolved.

### Tool(s) used

N/A

### The 5 W's

**Who caused the incident?**

The individual who conducted the forced browsing attack.

**What happened?**

The attacker exploited a vulnerability in the company's e-commerce web application, using a forced browsing attack to access customer PII and financial information.

**When did the incident occur?**

The incident was reported on December 28, 2022, at 7:20 p.m. PT, though the attacker first reached out on December 22, 2022, at around 3:13 p.m. PT. The security team then investigated the incident from December 28 to December 31, 2022.

**Where did the incident happen?**

At a mid-sized retail company.

**Why did the incident happen?**

The incident happened because the e-commerce web application didn't properly restrict access to purchase confirmation pages, so the attacker could pull up other customers' pages just by changing the order number in the URL, then collect and exfiltrate their data.

The attacker was likely motivated by financial gain, as they had emailed an employee twice, first requesting $25,000 in cryptocurrency, then increasing the demand to $50,000, in exchange for keeping the stolen data off public forums.

### Additional notes

Was the security team ultimately able to uncover the identity of the individual behind the attack, and whether they had any ties to the company (e.g., a disgruntled ex-employee)?

## Reflections/Notes

**Were there any specific activities that were challenging for you? Why or why not?**

The task I struggled with the most was the "Capture your first packet" activity. I am quite new to the field of network data, so seeing all of the packet data appear, especially as large blocks of raw data in the terminal, was a lot to take in at first and took me a bit of time to fully interpret and understand.

**Has your understanding of incident detection and response changed since taking this course?**

Yes. Going into this course, I only had a very general and vague idea of incident detection and response from the previous courses. However, this course really helped me clarify my understanding of each phase of the incident response lifecycle and the tools that help security analysts effectively detect and respond to security incidents.

**Was there a specific tool or concept that you enjoyed the most? Why?**

I really enjoyed applying filters in Wireshark, running tcpdump commands, and learning to read and write basic rules in Suricata. I think I have a mind that's very stimulated by computer coding, so it was really fun to learn more technical languages for security tools I will likely be using in the future.
