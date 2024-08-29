# RFC-000: Subdomain naming convention
## Summary
Use Subdomains instead of paths for more granular finetuning.
## Details
Main reason is if we only use subdomains we can remove locations based on service. if we use path then we have to remove the whole location if a single service is facing issues or getting overloaded.

This requries automation, which we will need anyway before onboarding.

Also for the naming, we should remove rpc. and sys. from the subdomain, the network name is already a unique identifier and the IBP is a rpc service. This makes it all look cleaner.
```
<networkname>.dotters.network
<networkname>.ibp.network
```
