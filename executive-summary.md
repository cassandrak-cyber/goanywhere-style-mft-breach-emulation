Executive Summary

Project Overview

The purpose of this project was to safely emulate the attack behavior observed during the 2023 GoAnywhere Managed File Transfer (MFT) breach. Rather than recreating the actual GoAnywhere vulnerability, I built a controlled lab environment to simulate the stages of the attack while focusing on threat emulation, detection opportunities, and incident response.

The lab used an Ubuntu virtual machine to represent a managed file transfer server containing realistic but fictional business data, including customer account records, employee payroll information, and vendor transfer requests. A Python HTTP server was used to simulate an exposed file transfer application. After verifying the service was accessible, I simulated an attacker discovering, collecting, staging, and preparing sensitive files for exfiltration.

Throughout the exercise, I documented each stage of the attack, mapped activities to the MITRE ATT&CK framework, preserved forensic evidence including HTTP server logs and SHA-256 hashes, and identified opportunities for detection and defensive monitoring.

Key Skills Demonstrated

* Threat Emulation
* Linux Administration
* Web Server Configuration
* MITRE ATT&CK Mapping
* Digital Forensics
* Data Staging
* Log Analysis
* Detection Engineering
* Security Documentation

Lessons Learned

This project reinforced that successful threat emulation is not only about demonstrating how an attack works, but also understanding how defenders can detect, investigate, and respond to malicious activity. It also highlighted the importance of protecting internet-facing file transfer systems, monitoring access to sensitive files, and preserving evidence during incident response.
