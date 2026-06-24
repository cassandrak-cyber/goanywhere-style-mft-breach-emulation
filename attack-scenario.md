# Attack Scenario

## Background

Managed File Transfer systems are commonly used by companies to exchange sensitive files with vendors, customers, and internal business units. Because these systems often contain confidential information, they are valuable targets for attackers.

In 2023, attackers exploited a vulnerability in GoAnywhere MFT environments and used that access to steal sensitive files. This lab recreates the behavior of that type of attack in a safe environment.

## Simulated Attack Chain

### Phase 1: Reconnaissance

The attacker identifies a web-based file transfer application exposed inside the lab network.

Example activity:

- Scanning for open ports
- Identifying web services
- Reviewing HTTP headers and login pages

### Phase 2: Initial Access

The attacker uses a purposely vulnerable web application to simulate exploitation of an exposed service.

This does not use the real GoAnywhere vulnerability. It only represents the concept of exploiting a public-facing application.

### Phase 3: Discovery

After gaining access, the attacker searches for files that may contain sensitive information.

Example test files:

- fake_customer_records.csv
- fake_employee_data.xlsx
- fake_vendor_transfer.txt

### Phase 4: Collection and Staging

The attacker copies test files into a staging folder before exfiltration.

### Phase 5: Exfiltration Simulation

The attacker transfers fake test files to another system inside the lab environment.

### Phase 6: Detection

Defensive controls are reviewed to identify suspicious behavior, such as:

- Unusual admin account creation
- Large file downloads
- Access to sensitive directories
- Unexpected outbound network traffic
