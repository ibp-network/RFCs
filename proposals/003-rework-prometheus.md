# RFC-000: Name Here
## Summary
Rework IBP prometheus instance to meet new bounty requirements and to increase performance. 
## Details
I would like to use 16-24 hours to revamp the prometheus monitoring setup.

- create downsampling rules
This will drastically increase Grafana dashboard performance and make it possible for us to publicly provide dashboards and reduce disk storage.
- implement alertmanager with webhooks to send alerts to our ibp alert channel.
- alerts
create alert rules for operational things, idea is in a second step to use this alert triggers to automatically take members out of the geodns pool, but this is out of this scope
- SLA monitoring of members

Everything will be done/documented with ansible and when we use it for auto removal we will need a second member running an instance.

Additionally going forward I would like to propose to charge the IBP for the monitoring according to our pricing model. Right now the prometheus instance has ~500GB of disk usage and required 16GB of memory and using 8 cores. With the new setup the storage and cpu usage will drastically decrease

## Notes
This discussion was held internally prior to this repo. After discussion the requested hours were increased to 16-32 hours.
