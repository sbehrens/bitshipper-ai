# 🚩 BitShipper AI – Incident Response Tickets (Fictitious)

---

### 🔴 **Incident #11: Unauthorized Production Release by Intern**
- **Summary**: A summer intern in Marketing improperly had production-level access due to unclear IAM role assignments and pushed faulty code, causing widespread outages for 2 hours.
- **Impact**:
  - Full logistics system downtime affecting all customers.
  - Approximately 300 delayed shipments, resulting in customer complaints.
- **Resolution Actions and Timelines/Delays**:
  - Immediate rollback executed within 2 hours.
  - Access-control audit initiated but stalled; permanent IAM overhaul delayed twice, now scheduled for next quarter due to prioritization conflicts.

---

### 🔴 Incident #12 – Customer Data Exposed in Data Lake
- **Summary**: Internal auditing revealed customer shipping addresses and contact details unintentionally stored in a publicly accessible AWS bucket for 3 days.
- **Impact**:
  - Sensitive data exposure affecting approximately 10,000 customers.
  - Risk of regulatory fines and customer trust erosion.
- **Resolution Actions and Timelines/Delays**:
  - Immediate bucket permissions correction (same-day).
  - Full investigation delayed for 2 weeks due to resource allocation conflicts. Remediation of underlying automated monitoring postponed.

---

### 🔴 Incident #13 – Supply Chain Library Vulnerability Patch Delayed
- **Summary**: BitShipper’s widely-used Java library (`QuickShip`) experienced a critical vulnerability; security team recommended immediate patching but execution delayed.
- **Impact**:
  - Vulnerability remained open in production for 10 days, increasing risk of data breaches.
  - Required emergency response disrupting development workflows.
- **Resolution Actions and Timelines/Delays**:
  - Emergency patching completed after significant delays due to lack of patching automation.
  - Proactive dependency scanning initiative postponed until following quarter due to resource constraints.

---

## 🔴 **Incident #16 – Unauthorized Internal Wiki Exposure**
- **Summary**: An internal documentation wiki containing strategic product roadmaps and financial forecasts was publicly accessible due to improper access controls, discovered after 5 days.
- **Impact**:
  - Potential loss of competitive advantage due to proprietary information exposure.
- **Resolution Actions and Timelines/Delays**:
  - Immediately secured wiki permissions.
  - Long-term RBAC solution for documentation delayed by 3 months due to competing priorities.

---

## 🔴 Incident #17 – API Failure due to Improper Permission Changes
- **Summary**: Unauthorized changes to API permissions by a junior engineer lacking proper access restrictions caused customer-facing APIs to fail intermittently for 4 hours.
- **Impact**:
  - Approximately 500 SMB customers unable to complete orders.
- **Resolution Actions and Timelines/Delays**:
  - Rolled back permissions within 90 minutes.
  - Proposed IAM overhaul delayed multiple times; implementation still pending.

---

## 🔴 Incident #18 – Unencrypted Customer Data Logged
- **Summary**: Due to a logging configuration error, customer credit card details were logged in plaintext internally for 7 days before detection.
- **Impact**:
  - Internal exposure of sensitive financial information, violating PCI compliance.
- **Resolution Actions and Timelines/Delays**:
  - Immediate log sanitization performed upon discovery.
  - Long-term data classification and logging standards delayed, awaiting internal agreement.

---

## 🔴 Incident #19 – Major API Outage Due to Unreviewed Code Deployment
- **Summary**: Unauthorized personnel from the analytics department deployed unreviewed code directly to production, resulting in API failure lasting 2.5 hours.
- **Impact**:
  - Halted logistics tracking services impacting thousands of real-time orders.
- **Resolution Actions and Timelines/Delays**:
  - Immediate rollback completed in under 1 hour.
  - Comprehensive access management controls and training delayed repeatedly; currently rescheduled for next quarter.

---

## 🔴 Incident #20 – Internal Payment System Data Leakage
- **Summary**: Employee compensation data mistakenly loaded into customer-facing analytics dashboards due to insufficient data governance controls, exposed internally for 14 days.
- **Impact**:
  - Internal employee relations concerns.
  - Compliance risk related to personal information handling.
- **Resolution Actions and Timelines/Delays**:
  - Removed data within 24 hours of identification.
  - Strategic initiative to establish formalized data governance repeatedly deprioritized, delaying implementation by 6+ months.

---

## 🔴 Incident #21 – Outage Caused by Improper Feature Flag Management
- **Summary**: An improperly configured feature flag disabled core tracking functionality in the customer portal, causing 4 hours of downtime during peak usage periods.
- **Impact**:
  - Disruption to 40% of customers during critical shipment windows.
- **Resolution Actions and Timelines/Delays**:
  - Quickly reverted feature flag in 2 hours.
  - Efforts to implement automated feature-flag governance delayed, deprioritized for 6 months due to lack of ownership.

---

## 🔴 Incident #21 – Container Deployment Registry Misconfiguration
- **Summary**: Misconfigured permissions allowed unrestricted push access to the internal container registry; inexperienced staff overwrote critical container images, causing intermittent outages over a 12-hour period.
- **Impact**:
  - Intermittent disruption across multiple customer-facing services.
- **Resolution Actions and Timelines/Delays**:
  - Restored container registry within one business day.
  - Proposed granular access controls for container registries delayed repeatedly, with no firm timeline for full implementation.