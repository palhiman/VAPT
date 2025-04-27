
# 📋 Web Application VAPT Checklist for Penetration Tester

**Target:** `whatever you decide` 
**Scope:** Web application only. Subdomains, infrastructure out-of-scope unless authorized. All of this is mentioned in contract document or Audit Requirement Sheet (ARS).

---

## **Phase 1: Reconnaissance & Information Gathering**

### Passive Reconnaissance
- [ ] Perform WHOIS lookup on domain.
- [ ] Enumerate DNS records (A, MX, TXT, SPF, CNAME).
- [ ] Gather SSL/TLS certificate information (SANs, issuer, expiration).
- [ ] Discover subdomains (e.g., `sublist3r`, `Amass`, online services).
- [ ] Identify technologies used (CMS, frameworks, libraries).
- [ ] Review historical snapshots via Wayback Machine.
- [ ] Search public breach databases and data leaks for target.

### Active Reconnaissance (Non-Intrusive)
- [ ] Identify open ports (safe scanning: e.g., `nmap` with -T3 or lower).
- [ ] Fingerprint web server and operating system (e.g., headers, `whatweb`).
- [ ] Conduct directory and file enumeration (`gobuster`, `dirsearch`, etc.).
- [ ] Map application structure, roles, user flows, API endpoints.

---

## **Phase 2: Vulnerability Assessment**

### Automated Scanning
- [ ] Configure and run OWASP ZAP / Burp Suite Scanner / Nikto.
- [ ] Target OWASP Top 10 vulnerabilities:
  - Injection flaws
  - Authentication/Session weaknesses
  - Sensitive data exposure
  - Broken access controls
  - Security misconfigurations
- [ ] Analyze scanner results and remove false positives.

### Manual Testing
- [ ] Test for SQL Injection (SQLi) manually.
- [ ] Test for Cross-Site Scripting (XSS) (Stored, Reflected, DOM).
- [ ] Test for Command Injection / OS Injection.
- [ ] Test for XML External Entity (XXE) attacks.
- [ ] Check for Cross-Site Request Forgery (CSRF).
- [ ] Test for Server-Side Request Forgery (SSRF).
- [ ] Check for Insecure Direct Object References (IDOR).
- [ ] Assess session management (cookie flags, insecure tokens).
- [ ] Test file upload functionalities (bypass extensions, upload shells - safely).
- [ ] Identify use of vulnerable components (e.g., outdated libraries).
- [ ] Look for security misconfigurations (verbose errors, default credentials).

---

## **Phase 3: Exploitation (Controlled)**

- [ ] Safely exploit vulnerabilities to demonstrate impact (no system damage).
- [ ] Document exploitation process, including:
  - Tools and payloads used
  - Exploitation steps
  - Impact assessment
- [ ] Capture evidence (screenshots, responses, logs).

### Privilege Escalation (Application Level)
- [ ] Attempt horizontal privilege escalation (e.g., regular user → another user’s data).
- [ ] Attempt vertical privilege escalation (e.g., regular user → admin).

### Lateral Movement (If Applicable)
- [ ] Identify trust relationships with external systems (APIs, integrations).
- [ ] Explore potential movement paths if authorized.

---

## **Phase 4: Reporting & Remediation Recommendations**

- [ ] Prepare a detailed technical report:
  - Summary of findings
  - Methodologies used
  - Risk ratings (High/Medium/Low or CVSS scores)
  - Detailed vulnerability descriptions
  - Exploitation evidence
  - Business impact analysis
  - Clear, actionable remediation steps
- [ ] Include all supporting evidence (screenshots, code snippets, logs).
- [ ] Prepare executive summary for non-technical stakeholders.
- [ ] Optional: Prepare a final presentation if requested.

---

## **Rules of Engagement**

- [ ] No Denial-of-Service (DoS) attacks.
- [ ] Minimize operational disruption.
- [ ] Cease testing immediately and report if major issues are found.
- [ ] Follow all ethical and legal standards.
- [ ] Document all actions, tools, and payloads used.

---

# ✅ Ready to Execute!

---
