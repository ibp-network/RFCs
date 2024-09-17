# RFC-005: Everyone deploys all chains
## Summary
Every member deploys all parachains that signed up. This comes at no additional cost to the bounty but with a slight increase in OPEX for the members for storage.
## Note
This discussion started before the existince of this repo but was not finished yet, due to this we are migrating this discussion to the new process and will attach some screenshots.
## Details
Tom had a great idea couple weeks back in the main channel.

All members will need to meet the hard requirements for Rank6 anyways, which is the expensive part. Instead of splitting the parachains amongst each other we all deploy all parachains that sign up. This will mean we only have a slight bigger disk usage but everything else you will already have.

This will drastically increase user experience and makes administration of it much simpler.
This will not generate additional costs to the treasury since payment will be calculated by % of usage. 

So we would take the global daily usage of each parachain from all IBP members then based on that calculate how % we all get paid from the global deployment.

For example >50M queries a day global amongst all Rank 6 members, full price.
5M queries, 10% of the price. Everyone will be paid based on their local compute pricing.
