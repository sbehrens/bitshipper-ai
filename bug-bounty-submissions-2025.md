# 🐛 BitShipper AI – Recent Bug Bounty Submissions (2025)

## Bug Bounty Program Overview

BitShipper AI launched its public bug bounty program in January 2024 through HackerOne. The program invites security researchers to identify and responsibly disclose security vulnerabilities in our platform. Below are the 10 most recently triaged submissions as of March 2025.

## Recent Submissions

| ID | Date | Vulnerability | Severity | Component | Status | Bounty |
|----|------|--------------|----------|-----------|--------|--------|
| BB-2025-042 | 2025-03-01 | Broken Access Control in User Profile API | High | User Service | Triaged | $3,500 |
| BB-2025-041 | 2025-02-28 | GraphQL Authorization Bypass | High | API Gateway | Fixed | $4,200 |
| BB-2025-040 | 2025-02-25 | IDOR in Shipment Tracking Endpoint | High | Tracking Service | Fixed | $3,800 |
| BB-2025-039 | 2025-02-22 | JWT Token Signature Verification Bypass | Critical | Authentication Service | Fixed | $7,500 |
| BB-2025-038 | 2025-02-20 | Missing Access Controls in Admin API | High | Admin Portal | Fixed | $4,000 |
| BB-2025-037 | 2025-02-18 | Cross-Site Scripting (XSS) in Customer Dashboard | Medium | Frontend Portal | Fixed | $1,800 |
| BB-2025-036 | 2025-02-15 | Privilege Escalation via Role Modification | High | User Service | Triaged | $3,500 |
| BB-2025-035 | 2025-02-12 | Improper Access Control in S3 Bucket Configuration | High | Data Storage | Fixed | $3,200 |
| BB-2025-034 | 2025-02-10 | IDOR in Customer Billing Records | High | Billing Service | Fixed | $3,800 |
| BB-2025-033 | 2025-02-08 | Cross-Site Scripting (XSS) in Shipping Label Generator | Medium | Shipping Service | Fixed | $1,500 |

## Detailed Findings

### BB-2025-042: Broken Access Control in User Profile API
**Severity: High**

The User Profile API endpoint allowed users to access and modify other users' profile information by simply changing the user ID parameter in the request.

**Affected Component**: userservice (Java/DGS/GraphQL)  
**Status**: Triaged, fix in progress  
**Remediation Plan**: Implement proper authorization checks to verify the requesting user has permission to access the requested profile

---

### BB-2025-041: GraphQL Authorization Bypass
**Severity: High**

The GraphQL API gateway had an authorization bypass vulnerability where nested queries could access data that should be restricted, even when the parent query had proper authorization checks.

**Affected Component**: graphqlgateway (TypeScript/Node.js/Apollo)  
**Status**: Fixed  
**Remediation**: Implemented field-level authorization checks and enhanced the GraphQL schema with proper access control directives

---

### BB-2025-040: IDOR in Shipment Tracking Endpoint
**Severity: High**

The shipment tracking endpoint was vulnerable to Insecure Direct Object Reference (IDOR) attacks, allowing authenticated users to access tracking information for any shipment by manipulating the tracking ID.

**Affected Component**: Tracking Service (Java/Spring Boot)  
**Status**: Fixed  
**Remediation**: Implemented proper authorization checks to verify the requesting user has permission to access the requested shipment

---

### BB-2025-039: JWT Token Signature Verification Bypass
**Severity: Critical**

A critical vulnerability in the authentication service allowed attackers to bypass JWT token signature verification by changing the algorithm specified in the token header from RS256 to HS256.

**Affected Component**: authsvc02 (TypeScript/Node.js/Passport.js)  
**Status**: Fixed  
**Remediation**: Updated JWT library, enforced specific algorithms, and implemented proper signature verification

---

### BB-2025-038: Missing Access Controls in Admin API
**Severity: High**

The Admin API lacked proper access controls, allowing any authenticated user to access administrative functions by directly calling the API endpoints.

**Affected Component**: Admin Portal (Java/Spring Boot)  
**Status**: Fixed  
**Remediation**: Implemented role-based access control (RBAC) and proper authorization checks for all admin endpoints

---

### BB-2025-037: Cross-Site Scripting (XSS) in Customer Dashboard
**Severity: Medium**

A stored XSS vulnerability was found in the customer dashboard where user-provided shipping notes were not properly sanitized before being displayed.

**Affected Component**: uiportal01 (TypeScript/React)  
**Status**: Fixed  
**Remediation**: Implemented proper output encoding and Content Security Policy

---

### BB-2025-036: Privilege Escalation via Role Modification
**Severity: High**

A vulnerability in the user management service allowed users to escalate their privileges by modifying their role in the user profile update request.

**Affected Component**: userservice (Java/DGS/GraphQL)  
**Status**: Triaged, fix in progress  
**Remediation Plan**: Implement server-side validation of role changes and restrict role modifications to authorized administrators

---

### BB-2025-035: Improper Access Control in S3 Bucket Configuration
**Severity: High**

An S3 bucket containing customer shipping labels and invoices had improper access controls, potentially allowing unauthorized access to sensitive documents.

**Affected Component**: Data Storage (AWS S3)  
**Status**: Fixed  
**Remediation**: Reconfigured bucket permissions, implemented proper IAM policies, and enabled bucket logging

---

### BB-2025-034: IDOR in Customer Billing Records
**Severity: High**

The billing service API was vulnerable to Insecure Direct Object Reference (IDOR) attacks, allowing users to access billing records of other customers by manipulating the record ID.

**Affected Component**: paymentsvc01 (Java/Spring Boot)  
**Status**: Fixed  
**Remediation**: Implemented proper authorization checks to verify the requesting user has permission to access the requested billing records

---

### BB-2025-033: Cross-Site Scripting (XSS) in Shipping Label Generator
**Severity: Medium**

A reflected XSS vulnerability was discovered in the shipping label generator where user input was not properly sanitized before being included in the generated label.

**Affected Component**: Shipping Service (Node.js/Express)  
**Status**: Fixed  
**Remediation**: Implemented input validation and output encoding

## Bug Bounty Program Statistics

- **Total Submissions (Lifetime)**: 187
- **Valid Submissions**: 112 (60%)
- **Bounties Paid (2025 YTD)**: $78,500
- **Average Time to Triage**: 2.3 days
- **Average Time to Fix**: 18 days
- **Most Common Vulnerability Types**:
  1. Broken Access Control (38%)
  2. Insecure Direct Object References (IDOR) (22%)
  3. Authentication Vulnerabilities (14%)
  4. Cross-Site Scripting (XSS) (12%)
  5. API Security Issues (8%)

## Strategic Considerations for Security Investments

1. **Access Control Framework Priority**: The high prevalence of access control issues (38%) and IDOR vulnerabilities (22%) across multiple services suggests a systemic architectural weakness rather than isolated implementation errors. Security investments should prioritize a company-wide access control framework with standardized implementation patterns rather than service-by-service fixes.

2. **Developer Education Focus**: The recurring nature of similar vulnerabilities across different services indicates knowledge gaps among development teams. Targeted security training focused specifically on access control implementation and JWT token handling would likely yield high returns.

3. **Automated Detection Capabilities**: The frequency of IDOR and access control issues suggests that current code review and testing processes are not effectively catching these vulnerabilities. Investments in automated scanning tools specifically calibrated for access control vulnerabilities could provide significant value.

4. **Technical Debt Correlation**: Many of the identified vulnerabilities appear in older services with known technical debt. This suggests that security investments should be aligned with technical debt reduction efforts rather than treated as separate initiatives.

5. **Avoid Premature Investment in Advanced Threats**: The bug bounty data shows that BitShipper AI is still struggling with fundamental security issues like access control. Investments in advanced threat protection would likely provide lower returns than addressing these basic security hygiene issues first.

6. **Measurement Opportunity**: The bug bounty program provides valuable metrics for measuring security improvement over time. Security investments should include resources for tracking the reduction in similar vulnerability types as a key performance indicator.