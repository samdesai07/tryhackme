## Introduction
Q. I'm ready to move on!
--> no answer needed

## What is Logged
KEY POINTS: Logging records OS and user events (e.g., login, file creation) to a journal.
It's critical for SOC activities like incident response and threat hunting.
Windows logs are stored as binary .evtx files in C:\Windows\System32\winevt\Logs.
Event Viewer is the tool to read these logs.
Key log entry details include Date/Time, Event ID, and Event Details.
Over 500 Security log Event IDs exist, but not all events are logged by default.

<img width="1280" height="398" alt="image" src="https://github.com/user-attachments/assets/d5e7a034-e8f1-4173-bbae-28af361856b4" />

Q. Looking at the last screenshot, which event ID describes a successful login?
(Answer format: LogSource / ID, e.g. Application / 8194)
--> Security / 4624 

## Security Log: Authentication
KEY POINTS: Windows Security Logs for SOC Analysts
The Security event log is the most valuable default Windows log for SOC analysts.
The two most important Security logs are:
Successful Logon (Event ID 4624): Used to detect suspicious logins (e.g., RDP, network) and find the starting point of an attack. It's logged on the target machine but can be very noisy, generating hundreds of events per minute on active servers.
Failed Logon (Event ID 4625): Used to detect brute-force attacks, password spraying, or vulnerability scans. It is also logged on the target machine but can be inconsistent and difficult to interpret correctly due to its complexities.
Structure and Usage
Even though a typical Windows login event (4624) has many fields, most cases can be handled by an L1/L2 analyst by focusing on just a few core fields.
Both 4624 and 4625 are vital for monitoring user activity and identifying potential security threats.

Q. Open the "Practice-Security.evtx" file on the VM's Desktop.
Which IP performed a brute force of the THM-PC?
--> 10.10.53.248

Q. Which user has been breached as a result of the attack?
--> administrator

Q. What was the Logon ID of the malicious RDP login?
Note: The login you are looking for has a Logon Type 10.
--> 0x183C36D

## Security Log: User Management
KEY POINTS: User Management Events: These logs are crucial for tracking user account history and detecting malicious activity.
Common Event IDs and Their Malicious Use:
4720, 4722, 4738: Account creation, enabling, or changes can signal a backdoor account.
4725, 4726: Disabling or deleting accounts might be done to hinder SOC analysts.
4723, 4724: Password changes or resets can indicate an attacker gaining access.
4732, 4733: Adding or removing users from security groups can be a sign of privilege escalation.
Event Structure: All user management events have a consistent structure with three main parts:
Subject: The account that performed the action (use the Logon ID to correlate with a login event).
Object: The target account of the action.
Details: Information about the changes made (e.g., new attributes, group name).
Real-World Usage: User manipulation events are common in real-world attacks, such as ransomware groups resetting passwords or attackers creating new admin accounts for persistence.

<img width="782" height="548" alt="image" src="https://github.com/user-attachments/assets/02edad24-4b5a-4824-814f-9cf527336005" />

Q. Continue with the "Practice-Security.evtx" file on the VM's Desktop.
Which user was created by the attacker soon after the RDP login?
--> svc_sysrestore

<img width="779" height="540" alt="image" src="https://github.com/user-attachments/assets/e5eae225-559d-4049-8b5b-0baf9bd8847a" />
<img width="783" height="538" alt="image" src="https://github.com/user-attachments/assets/defd592d-10dd-4b8a-a21e-58a0bab8e661" />

Q. Which two privileged groups was the backdoor user added to?
(Answer in alphabetical order, e.g. "Administrators, Power Users")
--> Backup Operators, Remote Desktop Users

<img width="779" height="542" alt="image" src="https://github.com/user-attachments/assets/dfb6acfc-4452-45c0-8d51-da7028d2f6ea" />

Q. Does the Logon ID field match what you saw in the previous task (Yea/Nay)?
--> Yea

## Sysmon: Process Monitoring
KEY POINTS: Process Monitoring Key Points
Process monitoring is crucial for SOC teams to understand how a system was breached, beyond just knowing who was involved.
Two main methods for process monitoring on Windows are:
Event ID 4688 (Security Log): Logs new process creation, including command line and parent process. It is disabled by default.
Sysmon (Event ID 1): A free, external tool from Microsoft that provides more advanced process creation details like process hash and signature. It is the preferred method for detailed monitoring.
Sysmon logs are found in the Event Viewer under Applications & Services -> Microsoft -> Windows -> Sysmon -> Operational.
Event ID 1 provides extensive details, grouped into:
Process Info: PID, path, and command line.
Parent Info: Parent process context, vital for building an attack chain.
Binary Info: Process hash and signature for advanced analysis.
User Context: The user running the process and their Logon ID.
Malicious indicators to look for in process monitoring logs include:
Processes running from uncommon directories (e.g., C:\Temp).
Suspiciously named processes.
A process's hash matching known malware on VirusTotal.
An unexpected parent process (e.g., Notepad launching a command prompt).

Q. 
