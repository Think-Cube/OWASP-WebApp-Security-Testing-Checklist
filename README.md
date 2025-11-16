# 🧰 OWASP Web Application Security Testing Checklist  
## Aligned with OWASP Web Security Testing Guide (WSTG v4.2 – Latest)

---

## 🕵️ 1. Information Gathering
- [ ] 🔍 Explore the application manually and identify entry points.  
- [ ] 🕸️ Perform automated crawling and hidden content discovery.  
- [ ] 📄 Review `robots.txt`, `sitemap.xml`, backups, temp files.  
- [ ] 🌐 Enumerate subdomains and related applications.  
- [ ] 🧩 Identify technologies, frameworks, and versions used.  
- [ ] 🖥️ Collect server and application fingerprints.  
- [ ] 🪶 Inspect HTML, comments, and metadata for sensitive info.  
- [ ] 👥 Identify all user roles and access levels.  
- [ ] ⚙️ List all hostnames, ports, and third-party integrations.  
- [ ] 🔗 Discover and analyze API endpoints (REST, GraphQL, gRPC).  

---

## ⚙️ 2. Configuration & Deployment Management
- [ ] 🧭 Identify admin interfaces or exposed management panels.  
- [ ] 🧹 Check for old, backup, or unreferenced files.  
- [ ] 🧱 Verify restricted HTTP methods (e.g., disable `PUT`, `TRACE`).  
- [ ] 🧾 Test for security headers (`CSP`, `HSTS`, `X-Frame-Options`, etc.).  
- [ ] 🔒 Validate HTTPS / TLS configuration and certificate chain.  
- [ ] 🧮 Confirm correct file permissions and environment variables.  
- [ ] 🚫 Ensure no production data in test systems (and vice versa).  
- [ ] ☁️ Test for exposed cloud storage or misconfigured CDN.  
- [ ] 🧩 Check for possible subdomain takeover or orphaned DNS entries.  
- [ ] 🧑‍💻 Review CI/CD pipelines for secrets or hardcoded credentials.  

---

## 👤 3. Identity Management
- [ ] 🆔 Review registration and provisioning flows.  
- [ ] 🚷 Test for user enumeration (login, reset, signup).  
- [ ] 👥 Verify unique username policies and predictable IDs.  
- [ ] 🔄 Validate de-provisioning and role removal processes.  
- [ ] ⚖️ Confirm least-privilege principles are applied.  

---

## 🔑 4. Authentication Testing
- [ ] 🔐 Verify credentials transmitted only via HTTPS.  
- [ ] 🚨 Test for default or weak passwords.  
- [ ] 🧭 Test for authentication bypass and forced browsing.  
- [ ] ⛔ Check brute-force protection and account lockout.  
- [ ] 🧾 Validate password policies (length, complexity, reuse).  
- [ ] 💾 Test “Remember Me” token security.  
- [ ] 🔁 Review password reset/change flows.  
- [ ] 🧠 Verify CAPTCHA / rate-limit on login endpoints.  
- [ ] 🛡️ Test MFA / 2FA enforcement.  
- [ ] 🚪 Ensure logout properly invalidates sessions/tokens.  
- [ ] 🧩 Test for session fixation and renewal upon login.  
- [ ] 🚫 Disable browser autocomplete on password fields.  
- [ ] 🧼 Verify sensitive data not cached or stored locally.  

---

## 🛂 5. Authorization Testing
- [ ] 📁 Test for path traversal and file access control.  
- [ ] 🧍 Test for insecure direct object references (IDOR).  
- [ ] 🔝 Check for privilege escalation (vertical/horizontal).  
- [ ] 🕳️ Test for missing or broken access control.  
- [ ] 🧱 Validate access control consistency across APIs.  
- [ ] 🪙 Review OAuth / OIDC implementations.  

---

## 🧩 6. Session Management
- [ ] 🍪 Identify how sessions are handled (cookies, tokens, JWT).  
- [ ] ⚙️ Verify cookie flags (`Secure`, `HttpOnly`, `SameSite`).  
- [ ] ⏰ Check session timeout and absolute expiration.  
- [ ] 🚪 Confirm session invalidation after logout or inactivity.  
- [ ] 🔁 Regenerate session IDs on login / privilege changes.  
- [ ] 🔒 Test session ID randomness and predictability.  
- [ ] 🧱 Validate HTTPS-only transmission of tokens.  
- [ ] 🧿 Test for CSRF and clickjacking protection.  
- [ ] 🪪 Review JWT signature, expiration, and claim integrity.  

---

## 🧮 7. Input Validation & Injection
- [ ] 💬 Test for Reflected, Stored, and DOM-based XSS.  
- [ ] 🧠 Test for SQL, NoSQL, and ORM Injection.  
- [ ] 🧾 Test for XML / XXE and XPath Injection.  
- [ ] 🧑‍💻 Test for Command, Code, and Template Injection (SSTI).  
- [ ] 🌐 Test for SSRF and HTTP Request Smuggling.  
- [ ] ⚙️ Test for HTTP Header and Host Header Injection.  
- [ ] 🚏 Test for Open Redirects.  
- [ ] 📂 Test for LFI / RFI (File Inclusion).  
- [ ] 🧱 Test for Expression Language Injection and Mass Assignment.  
- [ ] 🔄 Compare client-side vs. server-side validation rules.  

---

## 🚨 8. Error Handling & Logging
- [ ] 🧱 Test for verbose error messages and stack traces.  
- [ ] 🚫 Validate no sensitive data is leaked in errors or logs.  
- [ ] 📋 Confirm security events are logged and monitored.  
- [ ] 📡 Verify alerting for critical events (auth failures, privilege changes).  

---

## 🔐 9. Cryptography
- [ ] 🔑 Verify encryption of sensitive data (in transit + at rest).  
- [ ] 🧮 Test for weak / deprecated algorithms (MD5, SHA-1, RC4).  
- [ ] 🧂 Check proper salting and key derivation (PBKDF2, bcrypt, Argon2).  
- [ ] 🧰 Validate secure random number generation.  
- [ ] 🚫 Detect hardcoded keys or secrets.  
- [ ] 🪪 Validate certificate chain and expiry.  

---

## 🧠 10. Business Logic Testing
- [ ] ⚙️ Test for logic bypasses and workflow manipulation.  
- [ ] ⏳ Test for race conditions and timing attacks.  
- [ ] 📈 Validate business rule enforcement (limits, quotas).  
- [ ] 🧾 Test for missing non-repudiation controls.  
- [ ] 🧍‍♂️ Verify separation of duties and privilege boundaries.  
- [ ] 📂 Test for unsafe file uploads (type, size, path, scanning).  
- [ ] 🧨 Test for malicious file execution after upload.  

---

## 🧭 11. Client-Side Security
- [ ] 🧠 Test for DOM-based XSS and client-side injection.  
- [ ] 🪶 Test for HTML and CSS Injection.  
- [ ] 🌐 Check CORS configuration.  
- [ ] 🖼️ Test for clickjacking via frames/iframes.  
- [ ] 📬 Verify Web Messaging (postMessage) origins and targets.  
- [ ] 💬 Test WebSockets for authentication and origin checks.  
- [ ] 💾 Check browser storage (LocalStorage, IndexedDB) for secrets.  
- [ ] 🔁 Test for Reverse Tabnabbing and open redirects.  
- [ ] 🔐 Verify PWA / Service Worker caching security.  

---

## 🔗 12. API Security Testing
- [ ] 🌍 Enumerate API endpoints and parameters.  
- [ ] 🧱 Test for Broken Object Level Authorization (BOLA).  
- [ ] 🧾 Check for excessive data exposure in responses.  
- [ ] ⚙️ Test for input validation and rate limiting.  
- [ ] 🧩 Test for mass assignment and schema injection.  
- [ ] 🧭 Validate authentication and authorization consistency.  
- [ ] 🧰 Test outdated API versions and unprotected endpoints.  
- [ ] 🪶 Test GraphQL queries and mutations for injection or over-fetching.  

---

## 🧨 13. Denial of Service
- [ ] 🕳️ Test for resource exhaustion (CPU, memory, I/O).  
- [ ] ⏱️ Verify rate limiting and throttling mechanisms.  
- [ ] 🧮 Test for regex or SQL wildcard DoS.  
- [ ] 📦 Test oversized payload and file upload handling.  

---

## 🧾 14. Reporting & Documentation
- [ ] 🧭 Document all findings with WSTG IDs, risk level, and PoC.  
- [ ] 🗂️ Map findings to OWASP Top 10 categories.  
- [ ] 🧰 Provide clear remediation steps and references.  
- [ ] 🔐 Store test results securely and restrict access.  
