Attack Phase	Activity Performed	MITRE ATT&CK Technique	Technique ID
Reconnaissance	Identified the target server and verified network connectivity.	Active Scanning	T1595
Initial Access (Simulated)	Simulated an exposed managed file transfer application.	Exploit Public-Facing Application	T1190
Discovery	Browsed available business files through the web interface.	File and Directory Discovery	T1083
Collection	Downloaded customer, payroll, and vendor files using wget.	Data from Local System	T1005
Data Staging	Moved collected files into a staging directory.	Data Staged	T1074
Archive Creation	Compressed the staged files into stolen_company_data.zip.	Data Staged	T1074
Simulated Exfiltration Preparation	Prepared the archive for simulated exfiltration.	Exfiltration Over Web Service	T1567
