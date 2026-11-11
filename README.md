# OWASP Juice Shop — Web Application Security Assessment

## Project Overview

This project documents a hands-on web application security assessment using OWASP Juice Shop, an intentionally vulnerable web application.

The objective is to practice web application reconnaissance, API inspection, vulnerability identification, risk assessment, and security remediation recommendations in a controlled local lab environment.

## Lab Environment

- Operating System: Kali Linux (ARM64)
- Virtualization: Oracle VirtualBox
- Container Platform: Docker
- Target Application: OWASP Juice Shop
- Browser: Firefox
- Testing Scope: Localhost only

## Tools Used

- Docker
- Firefox Developer Tools
- OWASP Juice Shop
- Kali Linux

## Assessment Activities

1. Configured a local web application security testing environment.
2. Deployed OWASP Juice Shop using Docker.
3. Inspected application network traffic using Firefox Developer Tools.
4. Identified and examined API endpoints.
5. Reviewed API responses and application configuration.
6. Evaluated potential information disclosure risks.
7. Documented observations and security recommendations.

## Findings

Security observations and verified findings will be documented in the `findings` directory.

Each confirmed finding will include:

- Description of the vulnerability
- Affected endpoint
- Evidence
- Likelihood
- Potential impact
- Severity
- Recommended remediation

## Repository Structure

```text
juice-shop-security-assessment/
├── README.md
├── findings/
├── screenshots/
└── evidence/
```

## Disclaimer

This project was conducted in a controlled local testing environment using an intentionally vulnerable application.

No external systems or unauthorized targets were tested.

