# Web Application Vulnerability Assessment — DVWA (Findings Only)

**Target:** Local DVWA instance (`http://localhost/`)  
**Tester:** Vaishnavi (EHVaishnavi)  
**Date:** 2025-09-13

---

## Summary
Using **sqlmap**, a SQL injection vulnerability was confirmed in the DVWA application.  
The `users` table was successfully dumped, revealing usernames and plaintext/weakly hashed passwords.  
This is a **High severity issue** because it enables full account compromise.

---

## Evidence
- Screenshots of sqlmap execution and Burp intercepted requests are stored in the `evidence/` folder of this repository.  
- The evidence clearly shows:  
  1. sqlmap identifying the vulnerable parameter.  
  2. Database and table enumeration.  
  3. Dumped user credentials in plaintext.  
  4. HTTP request/response captured in Burp.

---

## Reproduction (short)
Example sqlmap command used:
```bash
sqlmap -u "http://localhost/vulnerabilities/sqli/?id=1" --data="id=1&Submit=Submit" -p id --batch --dump --output-dir=./evidence/sqlmap
