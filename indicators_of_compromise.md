Indicators of Compromise (IOCs)

Overview

This document identifies the indicators of compromise observed during the simulated GoAnywhere-style Managed File Transfer (MFT) breach. These artifacts represent evidence that defenders could use to detect, investigate, and respond to similar activity.

Network Indicators

* Multiple HTTP GET requests to sensitive business files.
* Consecutive requests made within a short period of time.
* Access to customer, payroll, and vendor records through the web service.

Host Indicators

* Creation of the staged_data directory.
* Creation of the stolen_company_data.zip archive.
* Downloaded copies of sensitive business files in the attacker workspace.

File Indicators

* customer_accounts.csv
* employee_payroll.csv
* vendor_transfer_requests.csv
* stolen_company_data.zip

Log Indicators

Observed HTTP GET requests included:

* GET /customer_accounts.csv
* GET /employee_payroll.csv
* GET /vendor_transfer_requests.csv

These requests demonstrate successful access to sensitive business files during the simulation.

Forensic Evidence

* SHA-256 hash generated for stolen_company_data.zip.
* Preserved HTTP server log entries.
* Screenshots documenting each stage of the attack.

Detection Opportunities

Security teams could improve detection by:

* Alerting on repeated access to sensitive business files.
* Monitoring for multiple downloads from managed file transfer systems.
* Detecting creation of ZIP archives containing confidential data.
* Reviewing web server logs for unusual download activity.
* Monitoring outbound transfers of archived business data.
