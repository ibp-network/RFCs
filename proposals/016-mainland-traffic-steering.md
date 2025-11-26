---

# RFC 016 – GeoDNS China Mainland Traffic Steering

## Summary

Authorize GeoDNS modification to route China mainland traffic from SEA region to
US West Coast (luckyfriday).

## Background

Rotko Networks currently handles 34.2% of IBP GeoDNS traffic volume (12.6M
requests), approximately 13x the volume of luckyfriday (779.4K requests).
Despite 2Gbps IPv4 and 12Gbps IPv6 transit capacity, MVR alerts occur during
peak hours due to China routing inefficiencies.

China premium transit pricing ranges $30-50/Mbit/s, with $25/Mbit/s as the
floor. Current IBP Asia reimbursement rate of $0.0731/GB does not support this.

## The China Boomerang

TSEA providers peer with Chinese ISPs at US West Coast exchanges. Traffic from
China to Hong Kong transits the Pacific twice aka. "the China Boomerang".

Bangkok → Hong Kong: 45ms  
Hong Kong → China mainland: +180ms (US West Coast round-trip)

Measured latencies ([source](https://ping.pe/160.22.181.181)):

| Rotko Bangkok → China | Latency |
|---|---:|
| Guangzhou (Tencent) | 221ms |
| Shanghai (Aliyun) | 211ms |
| Chengdu (Tencent) | 240ms |
| Hubei (China Unicom) | 377ms |

Luckyfriday US West ([source](https://ping.pe/64.62.224.18)):

| Luckyfriday → China | Latency |
|---|---:|
| Guangzhou (Tencent) | 180ms |
| Shanghai (Tencent) | 172ms |
| Chengdu (Tencent) | 203ms |
| Lishui (China Unicom) | 188ms |

US West Coast provides 30-50ms lower latency to China mainland than SEA
endpoints.

## Proposal

Upon passing, this RFC authorizes Rotko to implement GeoDNS steering rules
routing China mainland origin traffic from SEA to luckyfriday. GEODNS in its
current state does not have this feature set, but we are more than  happy to
implement it.

Load redistribution reduces peak hour pressure on highest-volume node while
improving latency for affected users.

---

## Vote

- 👍 = Aye
- 👎 = Nay

---
