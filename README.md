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


