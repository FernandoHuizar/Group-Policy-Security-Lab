Group Policy Security Lab
Overview
Designed and implemented enterprise Group Policy Objects (GPOs) on a Windows Server 2022 domain controller to enforce security controls across a multi-department Active Directory environment with 400+ users. All policies were built to reflect real-world compliance and security hardening standards used in enterprise environments.
Environment

Domain Controller: Windows Server 2022 (DC01)
Domain: corp.lab
Users: 400+ across 8 departments
Tool: Group Policy Management Console (GPMC)
<img width="1264" height="768" alt="image" src="https://github.com/user-attachments/assets/504c408e-9f74-4a18-a7bc-522583d87d4a" />

GPOs Implemented
1. CORP-Password-Policy (Linked to domain)
Enforced organization-wide password requirements:

Minimum password length: 12 characters
Maximum password age: 90 days
Minimum password age: 1 day
Password history: 10 passwords remembered
Complexity requirements: Enabled

2. CORP-Account-Lockout (Linked to domain)
Configured account lockout to protect against brute force attacks:

Lockout threshold: 3 invalid attempts
Lockout duration: 30 minutes
Reset counter after: 30 minutes
<img width="892" height="748" alt="image" src="https://github.com/user-attachments/assets/82266ff8-1daf-4e8e-83fa-7bfc6aa87753" />


3. CORP-Login-Banner (Linked to domain)
Deployed a legal warning banner displayed to all users before login, informing users that the system is monitored and restricted to authorized users only. Required for compliance in regulated environments.
4. CORP-USB-Block (Linked to Corp OU)
Blocked all removable storage access across the organization to prevent data exfiltration:
<img width="893" height="634" alt="image" src="https://github.com/user-attachments/assets/48291aea-d0eb-41cd-a50e-1f01cb394835" />

All Removable Storage classes: Deny all access
Removable Disks: Deny read access
Removable Disks: Deny write access
Security filtering configured to exclude GRP-IT so IT staff retain USB access for operational needs
<img width="892" height="569" alt="image" src="https://github.com/user-attachments/assets/14ee0e6f-6846-44fc-a3fe-bb512e176f46" />


5. CORP-Desktop-Lockdown (Linked to Finance-Accounting and Human-Resources OUs)
Applied desktop restrictions to Finance and HR departments handling sensitive data:

Prevented users from changing desktop background
Prevented users from changing screen saver
Blocked access to command prompt for non-technical users
<img width="881" height="684" alt="image" src="https://github.com/user-attachments/assets/3a42d52a-cd3e-4139-a703-07816aab4927" />


6. CORP-Audit-Policy (Linked to domain)
Enabled security auditing across the domain to log all critical events for compliance and incident response:

Audit account logon events: Success and Failure
Audit account management: Success and Failure
Audit logon events: Success and Failure
Audit policy change: Success and Failure
Audit privilege use: Success and Failure
<img width="899" height="624" alt="image" src="https://github.com/user-attachments/assets/39aa0fe2-9ff5-4cc9-8286-c25ad5822b6c" />


Key Concepts Demonstrated

GPO creation, linking, and scope management
Domain-level vs OU-level policy application
Security filtering to exclude specific groups from GPO scope
Least privilege enforcement through desktop restrictions
Compliance-driven audit logging aligned with SOX and security best practices
Defense in depth through layered security controls

