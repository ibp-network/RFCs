# RFC 013 – IBP Cost Reduction Measure

## Summary

DOT remains in the low single digits, Treasury purchasing power is depressed, and Bounty #50 is burning roughly **$275k/month**, leaving only a few months of viable runway. This RFC proposes new, lower IBP hardware pricing—effective **December 2025**—to materially reduce Treasury outflow, extend sustainability, and strengthen our commercial positioning with Parity, W3F, and other ecosystem clients.

**New infra pricing (effective December 2025 billing month):**

- CPU: **$14.172 → $10.00** per core/month  
- RAM: **$1.402 → $1.00** per GB/month  
- NVMe: **$0.193 → $0.10** per GB/month  

**Impact at the infra level:**

- Per‑member reduction: **$5,714.57/month**  
- Program‑wide reduction (12 members): **$68,574.82/month**  
- Infra component drops ~**42%**  
- Overall program burn drops ~**25%** (from ~$275k → ~$206k/month)

> **Note:** Bandwidth remains the dominant cost driver and is **unchanged**, which is why overall burn reduction (~25%) is smaller than the infra reduction (~42%).

---

## Current Setup

Each member operates:

- **240 cores**  
- **944 GB RAM**  
- **46,600 GB NVMe**  

**Current monthly per‑member (old pricing):**

- CPU: 240 × 14.172 = **$3,401.28**  
- RAM: 944 × 1.402 = **$1,323.49**  
- NVMe: 46,600 × 0.193 = **$8,993.80**  

**Total per member:** **$13,718.57**  
**Program total (12 members):** **$164,622.82/month** (infra only)  
Including bandwidth + other costs → **~$275k/month** total burn.

---

## Proposed New Pricing (Effective December 2025)

New unit prices:

- **CPU:** $10.00 per core/month  
- **RAM:** $1.00 per GB/month  
- **NVMe:** $0.10 per GB/month  

**New per‑member pricing:**

- CPU: 240 × 10 = **$2,400.00**  
- RAM: 944 × 1 = **$944.00**  
- NVMe: 46,600 × 0.10 = **$4,660.00**  

**New total per member:** **$8,004.00**  
**Reduction per member:**  
$13,718.57 − $8,004.00 = **$5,714.57/month**

**Program‑wide reduction (12 members):**  
12 × 5,714.57 = **$68,574.82/month**

**Updated total burn:**  
$275,000 − $68,574.82 = **≈$206,425/month**  

**Runway impact:**  
- At current burn (~$275k): ~4–5 months  
- At new burn (~$206k): ~6–7 months  
- **Runway extended by ~1.5–2 months**

---

## Why Now

- **Treasury pressure.** DOT price compression has reduced the purchasing power of Treasury‑denominated bounties. Preserving runway is critical before we request additional funding.  
- **Hardware economics have shifted.** The IBP hardware fleet is now ~3 years old, and market costs for CPU, RAM, and NVMe have materially decreased. Holding legacy pricing no longer aligns with real-world cost baselines.  
- **Commercial leverage.** Lower base rates strengthen IBP’s position when replacing Parity and W3F cloud spend. Competing directly with AWS/GCP/Cloudflare requires a more aggressive cost structure.  
- **Clean lever, zero operational risk.** Bandwidth remains the largest cost driver and cannot be reduced without impacting reliability. Adjusting CPU/RAM/NVMe pricing is the safest way to achieve meaningful savings without touching SLAs or capacity.  
- **Governance optics.** Showing fiscal discipline improves credibility ahead of any upcoming Treasury refills.

---

## Vote

On the GitHub RFC PR:

- 👍 **Thumbs up** = **Aye** (approve new pricing effective December 2025)  
- 👎 **Thumbs down** = **Nay** (reject proposal)

No reaction = abstain.
