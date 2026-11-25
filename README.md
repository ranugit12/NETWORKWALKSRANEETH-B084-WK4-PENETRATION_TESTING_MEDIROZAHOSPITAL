# NETWORKWALKSRANEETH-B084-WK4-PENETRATION_TESTING_MEDIROZAHOSPITAL
## Executive summary

In this project, I've conducted a Black-box Penetration test on my client **Mediroza General Hospital**. I have been instructed to conduct a security test on their web infrastructure. There were potential vulnerabilities that I've found. This project revealed several vulnerabilities where patients' files, which contained sensitive information such as: Doctor's name, Date of birth, test results were extractable from the patients' portal without credentials, personal information were available inside an SQL data which was received when pentesting through the website. This pentest is conducted with authorized access from the client starting from 23rd November 2026.

## Scope and Methodology

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


## Evidence of exploitation

Patient_report_1
<img width="1917" height="1077" alt="Password for Patient report 1" src="https://github.com/user-attachments/assets/f095c5e0-77e9-4248-9c4f-0048484a45c2" />
<img width="1917" height="1077" alt="Patient_report_1" src="https://github.com/user-attachments/assets/ce317207-6434-4da9-95e8-42eb302a3ef6" />

Patient_report_2
<img width="1917" height="1022" alt="Password for Patient report 2" src="https://github.com/user-attachments/assets/bec2513c-aa52-410a-882d-baa6de869cc9" />
<img width="1917" height="1077" alt="Patient_report_2" src="https://github.com/user-attachments/assets/871ded3f-5168-4e5a-badb-d3ebb95ac146" />

Patient_report_3
<img width="656" height="98" alt="Password for Patient report 3" src="https://github.com/user-attachments/assets/e0657f36-8b7d-451f-8b75-0a6f71f7414f" />
<img width="577" height="812" alt="Patient_report_3" src="https://github.com/user-attachments/assets/9d5115d6-0409-42dd-93f4-27fc7a986c58" />





