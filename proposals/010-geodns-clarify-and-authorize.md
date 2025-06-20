#####
RFC‑010: IBP‑GeoDNS — 2025 Hours Adjustment & Status Update  
#####

### 1  Summary  
This RFC corrects past billing discrepancies and requests an updated 2025 hour allocation for the **IBP‑GeoDNS** project. It also lists the feature set delivered to date, the issues that required refactoring, and the remaining 2025 work items.

---

### 2  Background & Billing History  

| Year | Source RFC(s) | Hours **authorised** | Hours **invoiced** | Delta |
|------|---------------|----------------------|--------------------|-------|
| 2024 | RFC‑004 | 200 | 200 | — |
| 2024 | RFC-009 (mis‑stated “240 h”) | 200 authorised, **240 paid** | 240 | **+40** (over‑payment) |
| 2025 *(current)* | RFC‑009 cap: 20 h / month → 240 h total | 170 paid (Apr + May) <br>130 pending (Jun) | **300** | **‑60** (over cap) |

*Key points*  
* Forty hours were inadvertently paid in 2024 that had **not** been authorised.  
* The 2025 limit of **20 h / month (240 h)** is already exceeded; after the June invoice only **−60 h** remain available for the rest of the year.

---

### 3  Request  

1. **Retroactively authorise** the 40 h already paid in 2024 (no new payment required—paperwork only).  
2. **Increase the 2025 monthly cap from 20 h to 30 h.**  
   *Adds 120 h* to the 2025 budget, raising the total to **360 h**.  
3. Recognise the 170 h already paid (Apr–May) and the 130 h June invoice (**300 h total**).  
4. This leaves **60 h** available for July – December 2025 for bug‑fixes and incremental features.

---

### 4  Feature Set Delivered to Date  

| Area | Highlights |
|------|------------|
| **Monitoring** | Modular check framework (ICMP, HTTPS/SSL, WSS, ACME HTTP‑01, IPv4/IPv6); per‑member thresholds; 10 s reaction time. |
| **GeoDNS Backend** | PowerDNS remote‑plugin; per‑service geo routing to closest latitude/longitude; dual‑stack (A/AAAA); static‑entry overlay. |
| **IBP‑Collator** | Aggregates check results, generates usage/billing CSV, publishes NATS messages for DNS node updates. |
| **ACME Automation** | Lets‑Encrypt certificate issuance from service path; shared on DNS nodes. |
| **P2P Consensus Layer** | Multi‑node validation to avoid false downtime; refactored into standalone executables to reduce mutex contention. |
| **Metrics Groundwork** | Initial Prometheus/Grafana queries prototyped (not yet feeding billing). |

---

### 5  Issues Encountered & Resolutions  

* **NATS message collisions / out‑of‑order data** — resolved by sequencing IDs and adding retry back‑off.  
* **Mutex contention in monolithic binary** — fixed via splitting into **monitor**, **dns‑backend**, and **collator** components.  
* **False “offline” events** — multi‑node quorum implemented.

---

### 6  Remaining 2025 Work  

* Modify WSS/endpoint check to include genesis‑block / hash validation (network assurance).  
* Draft and adopt a dedicated SLA in a separate RFC.  
* Pull Prometheus data directly from Grafana for consolidated metrics.  
* Update billing sheets to include Prometheus metrics and ibp‑geodns usage (uptime, hits).  
* Extend Matrix bot so members can manage status; add NATS handling so **ibpcollator** notifies **ibpdns** nodes when a member should be removed from rotation.  
* Implement a REST API on the collator exposing status and usage data from Grafana and ibpdns for external dashboards and sites.

---

### 7  Approval Requested  

 **MOTION**  
 *Approve RFC‑010 with the following points:*  
 1. Retroactive approval of the **40 h** over‑payment made in 2024.  
 2. Increase of the 2025 cap to **30 h per month** (total 360 h).  

