Attack Scenario

Scenario Overview

This project emulates the attack behavior observed during the 2023 GoAnywhere Managed File Transfer (MFT) breach in a safe, controlled lab environment. The objective was not to reproduce the actual GoAnywhere vulnerability, but to understand the attack lifecycle and demonstrate how similar attacker behavior could be detected and investigated.

In this lab, an Ubuntu virtual machine was configured to represent a managed file transfer server containing realistic but fictional business data. A Python HTTP server simulated an exposed web-based file transfer application. Representative files included customer account records, employee payroll information, and vendor transfer requests.

After verifying the service was accessible, the simulated attacker discovered the available files, collected the sensitive business data through the web service, staged the files into a single archive, and prepared them for simulated exfiltration. Throughout the exercise, server logs, forensic artifacts, and evidence were preserved to demonstrate how defenders could investigate and detect similar activity.

Attack Objectives

The simulated attacker attempted to:

* Identify an exposed managed file transfer service.
* Discover sensitive business documents.
* Collect valuable customer, employee, and vendor information.
* Stage the collected data into a compressed archive.
* Prepare the archive for exfiltration.
* Leave evidence that could later be identified through log analysis and forensic investigation.

Defensive Objectives

The purpose of this emulation was to help defenders understand:

* What evidence this type of attack leaves behind.
* How web server logs can reveal unauthorized file access.
* How file staging can indicate preparation for data theft.
* How MITRE ATT&CK techniques map to each phase of the attack.
* How organizations can improve detection and response for managed file transfer systems.

Ethical Statement

This project was performed entirely within an isolated lab environment using fictional business data. No real organizations, production systems, or customer information were targeted. The project focuses on understanding attacker behavior to improve defensive security practices.
