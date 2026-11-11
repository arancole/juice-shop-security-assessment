# Initial Web Application Assessment

## 1. Assessment Scope

Target: OWASP Juice Shop  
Environment: Local Kali Linux virtual machine  
Target URL: http://localhost:3000  
Testing Type: Authorized web application security assessment

## 2. Environment Setup

- Installed Docker on Kali Linux.
- Downloaded the OWASP Juice Shop Docker image.
- Deployed the application in a Docker container.
- Verified that the application was accessible through localhost.

## 3. Reconnaissance

### Browser Network Inspection

Used Firefox Developer Tools to inspect application network traffic.

Observed API requests including:

- server
- application
- challenges
- hackingInstructor
- products

### Products API

Inspected the products API response.

Observed fields:
- name
- description
- price

Assessment: The returned information appears consistent with normal product functionality. No vulnerability confirmed.

### Challenges API

Inspected the challenges API response.

Observed:
- Successful API response
- Challenge metadata
- Difficulty value

Assessment: The information appears consistent with the application's intended challenge functionality. No vulnerability confirmed.

### Application Configuration Endpoint

Endpoint:
`/rest/admin/application-configuration`

Observation:
The endpoint returned application configuration data without requiring authentication during initial testing.

Encryption-related configuration was observed.

Assessment: Potential information disclosure. Additional investigation is required to determine whether confidential information is exposed and whether access controls are appropriate.

## 4. Next Steps

- Examine the application configuration response.
- Verify whether sensitive information is exposed.
- Investigate authentication and authorization behavior.
- Document confirmed vulnerabilities.
- Assign risk ratings.
- Recommend remediation measures.




## 5. Access Control Testing

### Administrative Configuration Endpoint

Endpoint:
`/rest/admin/application-configuration`

Test Method:
Accessed the endpoint using a fresh Firefox private browsing session without logging into the application.

Result:
The endpoint returned configuration data without requiring an authenticated browser session.

Security Observation:
The endpoint appears accessible without authentication. This may represent an authorization weakness depending on the sensitivity of the returned configuration data.

Evidence:
- Screenshot: `03-application-configuration.png`
- Test environment: Local OWASP Juice Shop instance.

Status:
Requires further investigation to determine the sensitivity of exposed information and the associated security impact.
