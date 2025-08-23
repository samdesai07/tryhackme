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


