# OWASP Juice Shop Security Assessment Report

## 1. Executive Summary

A hands-on web application security assessment was conducted against a locally deployed OWASP Juice Shop instance.

The assessment focused on application reconnaissance, API response inspection, configuration exposure, and authentication behavior.

## 2. Scope and Environment

- Target: OWASP Juice Shop
- Target URL: http://localhost:3000
- Operating System: Kali Linux ARM64
- Container Platform: Docker
- Browser: Firefox
- Testing Scope: Local application only

## 3. Tools and Methodology

- Docker: Application deployment
- Firefox Developer Tools: Network traffic and API inspection
- Manual testing: Endpoint and authentication checks

Testing activities included:
- Application reconnaissance
- API endpoint identification
- JSON response inspection
- Unauthenticated endpoint access testing
- Evidence collection

## 4. Assessment Observations

### Observation 1: Products API

The products API returned product information including names, descriptions, and prices.

Assessment: Information appears consistent with expected application functionality. No vulnerability confirmed.

### Observation 2: Challenges API

The challenges API returned challenge metadata, including difficulty information.

Assessment: Information appears consistent with intended application functionality. No vulnerability confirmed.

### Observation 3: Administrative Configuration Endpoint

Endpoint:
`/rest/admin/application-configuration`

The endpoint returned application configuration data when accessed through a fresh private browsing session without authentication.

Encryption-related configuration and a security.txt link were observed.

Assessment: Potential information disclosure and access-control concern. Additional validation is required to determine whether confidential information is exposed.

## 5. Risk Assessment

Potential vulnerability: Unauthenticated access to administrative configuration information.

- Likelihood: Requires further evaluation.
- Impact: Depends on the sensitivity of the returned configuration data.
- Severity: Not assigned because a confidentiality impact has not been established.

## 6. Recommendations

1. Restrict administrative endpoints to authorized users.
2. Enforce server-side authentication and authorization checks.
3. Review configuration responses for unnecessary sensitive information.
4. Avoid exposing credentials, private keys, and secret values.
5. Apply least-privilege principles to administrative functionality.
6. Perform additional testing to validate access-control protections.

## 7. Conclusion

This project provided practical experience with web application reconnaissance, API inspection, authentication testing, and security documentation.

The assessment identified an administrative configuration endpoint accessible without authentication. Further validation is necessary before classifying this observation as a confirmed vulnerability.

## 8. Disclaimer

All testing was performed against an intentionally vulnerable application deployed locally for educational purposes. No external systems were targeted.
