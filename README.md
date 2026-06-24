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

- Kali Linux
- Vulnerable web application
- Windows or Linux target VM
- Wireshark
- Nmap
- Burp Suite
- Python simple HTTP server
- Sigma-style detection logic

## Attack Scenario

The simulated attack follows this general flow:

1. Reconnaissance of an exposed file transfer web application
2. Identification of a vulnerable service
3. Unauthorized access to the web application
4. Discovery of sensitive test files
5. Staging of files for exfiltration
6. Simulated data transfer to an attacker-controlled system
7. Detection and documentation of suspicious activity

## Important Ethical Note

This project is for educational and defensive purposes only. No real organizations, systems, credentials, customer records, or production environments were targeted. The lab uses only controlled virtual machines and test files.
