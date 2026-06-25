# goanywhere-style-mft-breach-emulation
Safe threat emulation of a GoAnywhere-style managed file transfer breach, including MITRE ATT&amp;CK mapping, detection engineering, and incident documentation.
# GoAnywhere-Style MFT Breach Emulation Lab

## Project Overview

This project is a safe, controlled lab that emulates the attack behavior seen in the 2023 GoAnywhere MFT breach. The purpose of this project is not to exploit the real GoAnywhere software, but to recreate the general attack chain in a legal lab environment so defenders can understand how this type of breach may occur and how it can be detected.

The 2023 GoAnywhere incident showed how attackers can target internet-facing file transfer systems, exploit a vulnerability, access sensitive files, and exfiltrate data. This lab focuses on threat emulation, detection engineering, and defensive documentation.

## Skills Demonstrated

- Threat emulation
- Vulnerability assessment
- Web application security testing
- Data exfiltration simulation
- MITRE ATT&CK mapping
- Detection rule development
- Incident documentation
- Security reporting

## Lab Environment

This lab was performed in an isolated environment using intentionally vulnerable systems and test data only.

Example lab tools:

- Ubuntu Linux virtual machine
- Kali Linux attacker workstation
- Python HTTP server simulating an exposed MFT application
- Simulated business data (.csv files)
- MITRE ATT&ck mapping
- Detection engineering documetation


## Attack Scenario

The simulated attack follows this general flow:

1. Reconnaissance of an exposed file transfer web application
2. Identification of a vulnerable service
3. Unauthorized access to the web application
4. Discovery of sensitive test files
5. Staging of files for exfiltration
6. Simulated data transfer to an attacker-controlled system
7. Detection and documentation of suspicious activity

8.# Phase 1 – Environment Preparation

A simulated Managed File Transfer (MFT) environment was created on an Ubuntu virtual machine. Representative business files were added to emulate the types of sensitive information attackers often target during data theft campaigns. Ubuntu machine getting ip address with ip -br addr command. Linux machine pinging ip addressing using ping command. 

If an attacker compromises a managed file transfer server, they’re usually looking for high-value business data, not random files.
Before emulating the attack, I created representative business data to simulate the types of files commonly stored on managed file transfer servers. This included customer account information and employee payroll data. All data was fictional and created solely for lab purposes. I created realistic but fake business documents because one of the primary objectives in attacks like the GoAnywhere breach is data theft rather than system destruction.


<img width="468" height="262" alt="image" src="https://github.com/user-attachments/assets/ba753354-9433-4110-93e6-dd7d96bf0f7a" />


Before interacting with a target, attackers typically verify that the host is reachable on the network. Was not able to demonstrate network communication in UOP vm environment. Pivotted to Ubuntu machine only.

<img width="468" height="245" alt="image" src="https://github.com/user-attachments/assets/7f754f4d-d35c-4ea2-b4f8-ebb647c52d62" />

<img width="468" height="272" alt="image" src="https://github.com/user-attachments/assets/b4487113-0070-4b8a-8996-03fe4b04a8be" />

<img width="468" height="310" alt="image" src="https://github.com/user-attachments/assets/f5e35b4b-5556-48da-b93d-0f4e8821e90b" />

<img width="468" height="283" alt="image" src="https://github.com/user-attachments/assets/3e0aa04b-7336-4c86-8109-ab3a75d08e13" />

Now we’re going to inspect them like an attacker would after gaining access. This represents the Discovery phase of the attack.
An attacker might ask:
•	Is this financial data?
•	Does it contain payroll?
•	Are there customer account numbers?
•	Is it worth stealing?
This maps to:
Discovery
•	T1083 – File and Directory Discovery
In the real GoAnywhere breach, attackers targeted a web-based file transfer application that organizations used to exchange files. We’re going to simulate that by hosting your fake business files with a simple web server. 



This represents the attacker’s target:
Initial Access
T1190 – Exploit Public-Facing Application
Simulated Managed File Transfer Server.


<img width="468" height="308" alt="image" src="https://github.com/user-attachments/assets/572085ac-a4e9-49e8-b982-b891af53da33" />

Since my university VMs can’t communicate with each other, we’re going to verify the service from the Ubuntu machine itself. This demonstrates that the service is running and serving files.

<img width="468" height="192" alt="image" src="https://github.com/user-attachments/assets/b4fe6226-71b9-42b1-b61a-dc4d89c9f5ae" />

Objective: Verify that the simulated managed file transfer server is accessible over HTTP.
Action: Started a local Python HTTP server and confirmed that representative business files could be viewed through a web browser.
Purpose: Demonstrate how an exposed file transfer service may present sensitive business data to an attacker after initial access.
MITRE ATT&CK: T1190 – Exploit Public-Facing Application (lab simulation).

Phase 2 – Reconnassaince 
•	Started a Python HTTP server.
•	Simulated an exposed MFT application.
•	Verified the service through a web browser.

Once the simulated MFT server was running, I accessed one of the fake customer files to emulate how an attacker would verify the value of the exposed data. At the same time, I reviewed the server logs to observe the HTTP GET requests that would provide forensic evidence during an incident investigation.

<img width="468" height="196" alt="image" src="https://github.com/user-attachments/assets/30733282-9301-4000-aae7-c9051849cc8c" />

This maps to:
Discovery
T1083 – File and Directory Discovery
Even though we’re opening the file in a browser, conceptually we’re discovering the contents of sensitive business data.

Phase 3 – Discovery 
•	Opened the sensitive files.
•	Verified their contents.
•	Documented why attackers would target them.
This phase maps to:
•	MITRE ATT&CK T1005 – Data from Local System

<img width="468" height="261" alt="image" src="https://github.com/user-attachments/assets/3c711be4-4688-457a-adad-c132ecf3a10c" />

<img width="468" height="256" alt="image" src="https://github.com/user-attachments/assets/6e284822-b4ec-427d-8ee0-395772f1083d" />

<img width="468" height="320" alt="image" src="https://github.com/user-attachments/assets/e0342019-0c9f-4381-b9bd-11c6113c939b" />

Phase 4 – Collection 
•	Downloaded the files using wget.
•	Created an attacker collection directory.
This is one of the phases that made the GoAnywhere breach so damaging.
The attackers didn’t immediately send every file they found across the network. They typically:
1.	Collected interesting files.
2.	Organized them.
3.	Compressed them.
4.	Then exfiltrated them.
We’re going to simulate that.
MITRE ATT&CK
This maps to:
T1074 – Data Staged

<img width="468" height="266" alt="image" src="https://github.com/user-attachments/assets/b82edee1-23f2-4b4a-af1d-d419dabf4d7b" />

Many threat actors compress data before exfiltration to reduce transfer time and package multiple files together. I wanted my emulation to reflect the behavior commonly observed during data theft operations rather than simply copying files.

<img width="468" height="295" alt="image" src="https://github.com/user-attachments/assets/92f41b47-b78d-48d4-9e84-b5493599b780" />

<img width="468" height="266" alt="image" src="https://github.com/user-attachments/assets/6ec2d3d6-59d0-4459-b4eb-b99e0942a104" />

Objective: Stage collected business data before simulated exfiltration.
Action: Moved the collected business files into a staging directory and compressed them into a ZIP archive.
Purpose: Threat actors commonly compress data prior to exfiltration to reduce transfer time, simplify data management, and package multiple files into a single archive.
MITRE ATT&CK: T1074 – Data Staged

Phase 5 – Data Staging 
•	Organized the files.
•	Compressed them into

One of the first places I’d look would be the web server access logs. In my lab, every file request generated an HTTP GET entry showing exactly which files were accessed and whether the request succeeded. I would use that information to identify unusual access patterns, such as multiple sensitive business files being downloaded within a short period of time.


<img width="468" height="278" alt="image" src="https://github.com/user-attachments/assets/588ff4d3-9ef6-4f54-9422-b3d83cc1995d" />

Web Server Evidence of File Access

Phase 6 – Forensics 
•	Generated a SHA-256 hash.
•	Preserved the web server logs.
•	Created evidence artifacts.
Before simulating exfiltration, I calculated a SHA-256 hash of the archive. In real incident response, hashes are used to verify file integrity and maintain evidence throughout an investigation.
This is the final stage of the attack.
In the real GoAnywhere breach:
•	The attackers found valuable files.
•	Collected them.
•	Compressed them.
•	Transferred them off the server.

<img width="468" height="286" alt="image" src="https://github.com/user-attachments/assets/031e3abb-87f5-48c6-b39a-067a53af1e99" />

A cryptographic hash acts like a fingerprint for a file.
If one single bit changes…
the hash changes.
That allows investigators to prove:
•	this is the same file
•	it wasn’t modified
•	evidence integrity was preserved

<img width="468" height="294" alt="image" src="https://github.com/user-attachments/assets/1a2895d4-c53d-4b17-a18b-aa85e20c735a" />

Recommendations to Edward Jones.
•	Don’t expose MFT servers directly to the internet.
•	Require MFA for administrative access.
•	Monitor for multiple downloads of sensitive files.
•	Alert when ZIP archives containing sensitive data are created.
•	Review HTTP GET requests for high-value files.
•	Segment MFT systems from internal networks.
•	Patch internet-facing applications promptly.
•	Audit third-party vendors with access to sensitive data.

<img width="468" height="264" alt="image" src="https://github.com/user-attachments/assets/f901e67e-5f5f-47ed-9e23-cf7a284dae91" />
































## Important Ethical Note

This project is for educational and defensive purposes only. No real organizations, systems, credentials, customer records, or production environments were targeted. The lab uses only controlled virtual machines and test files.
