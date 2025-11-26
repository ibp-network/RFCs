# RFC 015 – Mandatory IPv6 Adoption

## Summary

All IBP members must provide IPv6 addresses for their endpoints by January 31,
2026.

## Motivation

JAM is an IPv6-only network planned for launch Q3 2026. IBP proxies must support
IPv6 by Q1 2026 to be JAM-ready.

## Why All Members

AAAA records override A records in DNS resolution. If only partial members
provide IPv6 addresses, GeoDNS will route to the reduced set of IPv6-capable
endpoints. This degrades latency and coverage for all users as fewer geographic
endpoints are available.

100% member adoption is required to maintain current service quality when IPv6
is enabled.

## Proposal

| Requirement | Deadline |
|---|---|
| All members submit IPv6 addresses to config | January 31, 2026 |
| IPv6 endpoints operational and reachable | January 31, 2026 |

Members not compliant by deadline become ineligible for bandwidth reimbursement
at RFC-014 rates until compliant.

## Rationale

JAM's IPv6-only architecture requires IBP infrastructure to be fully
IPv6-capable before launch. Q1 2026 compliance gives 6 months buffer before Q3
2026 JAM launch for testing and integration.

---

## Vote

On the GitHub RFC PR:
- 👍 **Thumbs up** = **Aye**
- 👎 **Thumbs down** = **Nay**

No reaction = abstain.

---
