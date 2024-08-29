# RFC-000: Name Here
## Summary
IBP requires a custom dns server setup to be able to serve all subdomains via geodns, existing solutions generate 1000s of api calls and take hours to remove a location in case of an incident.
## Details
This room is regarding the ibp-geodns remote plugin that I made as part of the new subdomain naming convention.

Spending the time to do this was required because:

We will have ~160+ subdomains that need to be independently managed and monitored for providing service under the new rank 6 excluding the migration from subdirectories to subdomains for the existing level 2/4 services (rpc.dotters.network and sys.dotters.network). Without having an automatic DNS management and monitoring solution in place it makes the management of services impossible. For example, with my existing geodns provider, it would take hours and 10s of 1000s of api calls to update the endpoints for any members going offline. It already take 2-4 minutes to perform this update with only 3 subdomains (rpc. sys. and hydradx.paras).

So, I designed a remote plugin for the powerdns system that will provide automated dns resolution from simple configuration files in the ibp-network/config repo.

This remote plugin has the capabilities to.

1. Monitor every member's site (Ping, etc)
2. Monitor every endpoint on every member (SSL checks, WSS checks, etc)
3. Automatically derive members, services and associations from configuration files
4. Dynamically update based on members availability with 10 second reaction time
5. Is highly multithreaded (almost every operation is conducted in its own thread which speeds everything up and reduces timeout delays when a member is offline)
6. Is capable of allowing members to operate the dns servers while still allowing members the necessary ability to generate lets encrypt SSL certificates
7. Improves GeoDNS functionality by using the latitude/longitude of the client's site to find the closest server to them. Presently, we're only able to have resolution down to the country level. With this, we could have 2, 3, or 10 sites in a single country and the client would be routed to the closest location.
8. Allows for more advanced functionality down the line
9. Allows other IBP members to help manage the DNS (if myself or milos is on vacation, for example)
10. Checks are modular in nature and self-contained. It's possible to add checks without modifying other code.
11. Simplifies geodns configuration for other members in the future that wish to run a geodns endpoint. It makes it as easy as inputting some configuration entries. This would be ideal once we're confident in it and members have begun operating dns resolution for existing domains (ibp.network and dotters.network)

In total, I've spent well over 300 hours on this. Some of that was already paid for previously (previous work done on health checks, etc), some of that is dual use and I will be able to use it in the Agents Program. But in total for writing, testing, rewriting, bug fixes, etc that I've done so far specifically for producing this module has been about 120 hours. I'm requesting an allocation of 200 hours for producing this. That would cover 120 hours already spent along with 80 hours of future bug fixes, feature integrations, etc. I know tugy is quite keen for instance to integrate prometheus data / grafana data into the health checker. I'd need to make a new check module for this. In the future once the 80 hours have been used I will make a new request for additional support time.

The total requested allocation is 120 hours retroactively ($10,200) and 80 hours of future work ($6,800) for a total of $17,000 payment in this upcoming payment period for July.

Github Codebase Repo: https://github.com/ibp-network/ibp-geodns
Members Configuration file: https://github.com/ibp-network/config/blob/main/members_professional.json
Services Configuration file: https://github.com/ibp-network/config/blob/main/services_rpc.json
Static DNS entries file: https://github.com/ibp-network/config/blob/main/geodns-static.json (This includes all static entries including www.dotters.network, _acme-challenge, etc)

You can test it by doing dns lookups against 72.49.17.46 as a nameserver. It will only respond to ibp.network and dotters.network domains that are listed in the services file or static entries file. This is a development node, so may not be fully reliable if I'm doing stuff.

The state of the code currently is in initial testing. I will be deploying 2 nodes for stability testing. I will move over to production testing after about 1-2 weeks (or whenever I feel confident in its ability to handle the load).

If anyone has any questions or wants a walk through of the code let me know. Basically, this just makes management of the IBP super easy and simple. It allows Tugy who's currently acting administrator to manage almost everything by himself.

## Notes
This discussion was held internally prior to this repo.
