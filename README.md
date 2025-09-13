# DVWA SQL Injection Assessment

## Overview
This repository contains evidence and findings from a web application vulnerability assessment of DVWA (Damn Vulnerable Web Application). The assessment focused on **SQL Injection vulnerabilities** using tools such as sqlmap and Burp Suite.

## Folder Structure
- `evidence/` — Screenshots of sqlmap execution, Burp request captures, and terminal logs.  
- `report/` — Markdown report (`webapp-assessment.md`) summarizing findings, reproduction steps, and recommended remediation.

## Tools Used
- DVWA (local vulnerable instance)  
- sqlmap  
- Burp Suite (Community Edition)  
- Kali Linux

## Summary
Sqlmap successfully exploited a SQL injection vulnerability in DVWA, dumping the `users` table containing usernames and plaintext/weak passwords. Remediation recommendations are included in the report.

## How to View
- Open `report/webapp-assessment.md` to see the full findings and screenshot captions.
