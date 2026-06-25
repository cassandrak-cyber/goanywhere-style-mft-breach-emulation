Lab Setup

Objective

Build a controlled lab environment to safely emulate the attack behavior observed during the 2023 GoAnywhere Managed File Transfer (MFT) breach.

Lab Environment

Host Platform

* University of Phoenix Virtual Lab

Operating Systems

* Ubuntu Linux (Simulated Managed File Transfer Server)

Software Used

* Python 3 HTTP Server
* Nano Text Editor
* wget
* zip
* sha256sum

Simulated Business Data

The Ubuntu server hosted representative business files created specifically for this exercise.

* customer_accounts.csv
* employee_payroll.csv

All data contained fictional information created for educational purposes.

Lab Workflow

1. Created representative business files.
2. Configured a Python HTTP server to simulate an exposed managed file transfer application.
3. Verified the service through a web browser.
4. Simulated discovery of sensitive files.
5. Collected the files using wget.
6. Staged the files into a dedicated directory.
7. Compressed the staged data into a ZIP archive.
8. Calculated a SHA-256 hash of the archive.
9. Preserved HTTP server logs as forensic evidence.
10. Documented findings, mapped activity to MITRE ATT&CK, and identified detection opportunities.
