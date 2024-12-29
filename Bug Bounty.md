# Bug Bounty Testing Tools and Resources Guide

## Proxy Tools
- **Burp Suite**: Industry-standard web security testing tool
- **Caido**: Modern web security testing tool
- **OWASP ZAP**: Free and open source web app scanner

## Vulnerable Web Applications for Practice
- **DVWA (Damn Vulnerable Web Application)**
- **OWASP Juice Shop**
- **Mutillidae II**
- **BWApp (Buggy Web Application)**
- **Hacker101**
  - Training site: [hacker101.com](https://hacker101.com)
  - CTF platform: [ctf.hacker101.com](https://ctf.hacker101.com/)

## Project Discovery Tools

### Nuclei
- Customizable vulnerability scanner based on YAML templates
- Supports multiple protocols and attack vectors

### Subfinder
- Passive subdomain enumeration tool
- Leverages dozens of APIs for comprehensive results

Example usage:
```bash
# Single domain scan
subfinder -d hackerone.com

# Multiple domains from file
subfinder -dL targets.txt
```

## Reconnaissance Tools

### HTTPx
- Fast and multi-purpose HTTP toolkit

### Aquatone
- Visual inspection of websites across multiple hosts

Example usage:
```bash
cat alive_targets.txt | aquatone
```

### Dirsearch
Directory enumeration tool with extensive features

Example usage:
```bash
# Basic scan
dirsearch -u https://hackerone.com -o directory.txt

# Multiple targets
dirsearch -l targets.txt -o directory.txt

# Advanced scan with filters
dirsearch -u https://hackerone.com \
  -i 200,204,403,443 \
  -x 500,502,429,581,503 \
  -R 5 \
  --random-agent \
  -t 50 \
  -F \
  -w wordlistdir.txt \
  -o directory.txt
```

## Historical Analysis Tools

### Wayback Machine
- Access archived versions of websites
- Tools available:
  - waybackurls
  - [web.archive.org](https://web.archive.org)

## Additional Resources

### DNS Enumeration
- [DNSdumpster](https://dnsdumpster.com/): Free domain research tool

### Security Tools
- [White Rabbit Neo](https://app.whiterabbitneo.com/)
- [403jump](https://github.com/trap-bytes/403jump)

### Vulnerability Assessment
- [CVSS Calculator](https://www.first.org/cvss/): Common Vulnerability Scoring System

## Common Vulnerability Types to Test
- Open Redirect
- Broken Access Control

## Tips
- Look for documents or files with "confidential" in the footer
- Always follow responsible disclosure guidelines
- Document your findings thoroughly
- Stay updated with latest security trends and vulnerabilities
