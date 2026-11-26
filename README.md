# NETWORKWALKSRANEETH-B084-WK4-PENETRATION_TESTING_MEDIROZAHOSPITAL
## 📌Executive summary

In this project, I've conducted a Black-box Penetration test on my client **Mediroza General Hospital**. I have been instructed to conduct a security test on their web infrastructure. There were potential vulnerabilities that I've found. This project revealed several vulnerabilities where patients' files, which contained sensitive information such as: Doctor's name, Date of birth, test results were extractable from the patients' portal without credentials, personal information were available inside an SQL data which was received when pentesting through the website. This pentest is conducted with authorized access from the client starting from 23rd November 2026.

## 🔭 Scope and Methodology

| Tools | Purpose |
| -----------| -------- |
| dnsrecon       | Enumerate all DNS records (NS, MX, SPF, TXT, SRV) |
| whois | Find domain registration details (owner, dates, name servers | 
| whatweb | Fingerprint web technologies (server, CMS, plugins, IP) | 
| nslookup | Resolve the domain name to its IP address using DNS |
| curl -I | Read the HTTP response headers of the website |
| wafw00f | Detect whether a Web Application Firewall protects the site |
| JTR (John the Ripper) | Used to extract the passwords for the PDFs via their hashes |
| Kali Linux & Windows | Operating systems used for reconnaissance activities |

| Parameter | Information |
| -----------| -------- |
| Target | https://medirozahospital.com |
| Approach  | Testing is only to be conducted within boundaries with appropriate consent from the client|
| Duration  | 3 days starting from 23rd November 2026  |


## 🔍Evidence of exploitation

Patient_report_1
<img width="1917" height="1077" alt="Password for Patient report 1" src="https://github.com/user-attachments/assets/f095c5e0-77e9-4248-9c4f-0048484a45c2" />
<img width="1917" height="1077" alt="Patient_report_1" src="https://github.com/user-attachments/assets/ce317207-6434-4da9-95e8-42eb302a3ef6" />

Patient_report_2
<img width="1917" height="1022" alt="Password for Patient report 2" src="https://github.com/user-attachments/assets/bec2513c-aa52-410a-882d-baa6de869cc9" />
<img width="1917" height="1077" alt="Patient_report_2" src="https://github.com/user-attachments/assets/871ded3f-5168-4e5a-badb-d3ebb95ac146" />

Patient_report_3
<img width="656" height="98" alt="Password for Patient report 3" src="https://github.com/user-attachments/assets/e0657f36-8b7d-451f-8b75-0a6f71f7414f" />
<img width="577" height="812" alt="Patient_report_3" src="https://github.com/user-attachments/assets/9d5115d6-0409-42dd-93f4-27fc7a986c58" />

Staff information including doctors
<img width="1917" height="877" alt="Staff info " src="https://github.com/user-attachments/assets/beff0257-a041-4035-a351-cd5527accb96" />

Lab reports of patients after login into the patients' portal
<img width="1919" height="1047" alt="Lab reports of patients" src="https://github.com/user-attachments/assets/37df6159-442d-4f95-9b61-ac11d58a898a" />

Using SQL payload to log into the form.
<img width="1919" height="1047" alt="Login into the portal with SQL payload" src="https://github.com/user-attachments/assets/d0a1bcc9-3580-4df6-9b79-232e211e1be9" />

Robots.txt file with 3 folders: ``/Patient/``, ``/Staff/``, ``/old/``(Where is found the SQL database with the staff information)
<img width="1919" height="1047" alt="Robots txt" src="https://github.com/user-attachments/assets/c270e704-356d-401a-8e45-327c52d640ae" />

Hospital staff information within the ``/old/`` directory
<img width="1919" height="1047" alt="Hospital Staff information" src="https://github.com/user-attachments/assets/6a469e5a-caa3-4ddc-812a-8f44d6a09cf2" />

WafW00f command
<img width="1919" height="344" alt="Wafw00f" src="https://github.com/user-attachments/assets/2aa51463-6cdf-4b65-a2ec-c2e7473f9d41" />

nslookup, whatweb, curl -I commands
<img width="1919" height="528" alt="nslookup, whatweb, curl" src="https://github.com/user-attachments/assets/9e4b133a-0c5b-4531-83c4-44570300b120" />

dnsrecon -d
<img width="1919" height="633" alt="dnsrecon" src="https://github.com/user-attachments/assets/84cf73ef-72db-4cd1-bb94-8b53a89c3675" />

whois
<img width="1919" height="1042" alt="whois" src="https://github.com/user-attachments/assets/204a96cf-5fac-4bc5-9a52-e1feab43451e" />
<img width="1919" height="1042" alt="Screenshot From 2026-11-23 05-23-01" src="https://github.com/user-attachments/assets/34dc4129-3134-4032-bde2-f63f08f5e5df" />
<img width="1919" height="271" alt="Screenshot From 2026-11-23 05-23-16" src="https://github.com/user-attachments/assets/5322d60d-0f92-4b61-b370-32af9190171c" />

SQL error revealed
<img width="1919" height="1012" alt="SQL error revealed" src="https://github.com/user-attachments/assets/c2fc9112-460b-4d48-aae7-ed5a96e7dd9d" />


## ⚠️ Risk Rating

| Finding | Severity | Rationale |
| ---------- | ---- | --------| 
|Patients' portal is vulnerable to SQL injections | 🔴 Critical | Allows authentication bypass and potential direct database extraction or compromise of the underlying application. |
| Patients' reports were extractable after login into the portal with Payload (Without credentials) | 🔴 Critical | Exposes confidential medical records of the patients resulting in an impact on privacy and compliance. |
| Passwords are guessable on the extracted reports | 🟠 High | implementing weak passwords on PDFs can make it easy for threat actors to obtain access to the sensitive information in the reports |


## 🔨 Recommendations and Remediations

1. **Enhance strong authentication on the login form with parameterized queries**: Use bound parameters to pass user input instead of constructing SQL statements by concatenating strings. Even if the user inputs a malicious SQL statement such as ``' OR 1=1 --``, the database sees it as plain text only.
2. **Strengthen password protection of patients' reports**: Use PDF encryption and access controls for keys for securing patient PDF files rather than depending on simple password protection.
3. **Add rate limiting and account lockout**: Enforce repeated failed login attempts to a certain limit. So that after the limit, the account is lockout so the file cannot be unlocked and extracted. This helps to prevent brute-force attacks.

## 🔴Warning
These information is to be used legally for company security improvements. Any misuse will result in penalties and other legal action taken against those who misuse this information.

## 🧑‍🦱 Project author
Raneeth Jayaratne 

## ℹ️ Project information
Program name: Cybersecurity intern @NETWORKWALKS | Batch: B084E
