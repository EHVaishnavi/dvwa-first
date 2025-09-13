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

## Evidence / Screenshot Captions
- Screenshot_2025-09-13_05_57_09.png — Sqlmap request to DVWA (initial target parameter).
- Screenshot_2025-09-13_05_57_30.png — Sqlmap database/table enumeration.
- Screenshot_2025-09-13_05_57_44.png — Partial `users` table dump (usernames + passwords).
- Screenshot_2025-09-13_05_58_02.png — Additional `users` table rows.
- Screenshot_2025-09-13_05_58_07.png — Sqlmap output files exported.
- Screenshot_2025-09-13_05_58_53.png — Burp intercept of exploited request.
- Screenshot_2025-09-13_05_58_58.png — Terminal log of sqlmap command/output.


---

## Reproduction (short)
Example sqlmap command used:
```bash
sqlmap -u "http://localhost/vulnerabilities/sqli/?id=1" --data="id=1&Submit=Submit" -p id --batch --dump --output-dir=./evidence/sqlmap

