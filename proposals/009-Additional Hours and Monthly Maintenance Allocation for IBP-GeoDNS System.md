# RFC-009: Additional Hours and Monthly Maintenance Allocation for IBP-GeoDNS System

## Summary

We propose a request for 66 additional development hours to reconcile the difference between originally approved time and actual work completed, alongside a monthly limit of up to 20 hours for ongoing maintenance and feature updates. The IBP-GeoDNS system has been significantly refactored to streamline future development, potentially allowing on-chain integration for DNS and monitoring operations.

## Details

The initial allocation of 240 hours proved insufficient due to unforeseen complexities in building a distributed billing mechanism and a peer-to-peer (P2P) consensus layer for uptime tracking. During implementation:

- False Downtime Detection: We encountered issues where members were incorrectly flagged as offline, prompting the development of multi-node validation.
- Refactoring: The code base was reorganized to separate monitoring and DNS functionalities, enabling simpler standalone executables for Windows or Linux.
- On-Chain Integration Prospects: The P2P code lays groundwork for potential on-chain governance, such as voting on DNS record changes or billing adjustments.

These efforts, combined with extensive troubleshooting and testing, totaled 306 hours—66 hours above the originally approved 240. We request approval for the additional 66 hours to address this overrun. Going forward, a 20-hour monthly limit for maintenance and enhancements will ensure predictable resource usage and budget control.

## Benefits and Drawbacks

Refactoring and the new P2P approach provide several key advantages:

- Easier Long-Term Maintenance: Modularity reduces the complexity of future updates and bug fixes.
- Distributed Monitoring: Multiple nodes validate uptime, minimizing false alerts and improving billing accuracy.
- Scalability & On-Chain Integration: The system is now better positioned for optional governance or DNS resolution features on the blockchain.

However, this extra work requires an unplanned increase in budget. There is also a learning curve for contributors adopting the refactored structure, and the potential on-chain features may introduce new overheads if pursued.

## Costs or Resource Requirements

We request 66 additional development hours to cover the shortfall, bringing the total hours for this project to 306. Afterward, we propose a maximum of 20 hours per month for maintenance and incremental improvements. Infrastructure requirements remain largely unchanged, relying on the existing DNS servers and monitoring nodes, with optional on-chain data storage or governance features adding only modest overhead.

## Next Steps

- Implement DNS Nodes on Member Sites: Deployment is planned for early January with selected members (Stake Plus, Metaspan, Amforc, and Rotko) hosting DNS services.
- Finalize Billing Report Generation: By early to mid-January, the automated reporting system will be completed to track member service uptime and calculate payouts.
- Begin System Usage: The revised billing model and refactored DNS infrastructure will be fully implemented starting in January, serving as the first month to employ all new features.

## Notes

The new code structure simplifies future enhancements, including the creation of standalone monitoring services and the potential for user-driven DNS configurations. Although on-chain voting and DNS storage are currently optional, their implementation is facilitated by the completed refactoring, offering a clear path for the project’s evolution based on community interest and resource availability.
