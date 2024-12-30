# Bug Bounty Methodology Guide

## Essential Tools

The WayBack Machine is an online tool that allows users to access archived versions of websites from the past. Usage:

```bash
echo 'https://hackerone.com/' | waybackurls > lists.txt
cat domains.txt | waybackurls > urls
```

Access through web.archive.org:
```
https://web.archive.org/cdx/search/cdx?url=bugbountyhunter.xyz/*&output=text&fl=original&collapse=urlkey
https://web.archive.org/cdx/search/cdx?url=*bugbountyhunter.xyz/*&output=text&fl=original&collapse=urlkey&filter=statuscode:200
```

## Methodology and Techniques

### Understanding the Scope
- Reconnaissance
  - Passive Recon
    - Use tools like subfinder, amass, sublist3r for subdomain enum
    - Leverage open source tools available online to gather information
  - Active Recon
    - Identifying web technologies with different tools
    - Checking and studying the application feature

### Target Analysis
- Map the target application's structure (e.g., sitemaps, API endpoints)
- Understand workflows and how users interact with the system

### Identifying Vulnerabilities

Test for common issues from OWASP Top 10:
- Input validation flaws (XSS, SQL Injection)
- Access control weaknesses (IDOR, privilege escalation)
- Authentication vulnerabilities (brute force, session management issues)
- Business Logic flaws

## Bug Triage Process

1. **Receive Reports**: Bug reports submitted via platform or portal
2. **Initial Assessment**: Validate scope and reproducibility
3. **Technical Analysis**: Reproduce and analyze impact/severity
4. **Documentation**: Create detailed issue rundown
5. **Assign Report**: Route to appropriate team/individual
6. **Resolution**: Implement and verify fix

## Tips & Tricks

1. Stay within the scope
2. Be concise
3. Be patient
4. Be consistent
5. Focus on specific bug categories at a time
6. Widen your skill repertoire
7. Focus on impact-driven findings
8. Avoid theoretical scenarios
9. Include visual evidence

## Report Template

```markdown
**Title:** [TITLE OF YOUR REPORT]

**CVSS v3:** [CVSS VECTOR STRING]
**CVSS Score:** [CVSS SCORE]
**Severity Rating:** [LOW, MEDIUM OR HIGH BASED ON CVSS]

**Vulnerability Type:** [CLASSIFICATION OF VULNERABILITY]

**Description:** [DESCRIPTION OF VULNERABLE COMPONENT, 2-3 PARAGRAPHS]

**Target:** [AFFECTED AREA/COMPONENT]

**Impact:** [SECURITY IMPACT ASSESSMENT]

**Steps to Reproduce:** [DETAILED REPRODUCTION STEPS]

**Recommendation:** [REMEDIATION ADVICE]
```

## Cross-site Scripting (XSS) Overview

### How XSS Works
Two stages to a typical XSS attack:
1. Attacker finds way to inject malicious code into web page
2. Victim visits the compromised page

### Impact
- Stealing sensitive information (session tokens, cookies, credentials)
- Injecting malware
- Modifying website appearance for malicious purposes

### Mitigation
- Identify injection points
- Implement input validation
- Avoid placing user input in dangerous contexts
