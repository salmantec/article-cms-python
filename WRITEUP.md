# Write-up : Comparison of VM vs App Service for this CMS App

### Analysis.

Scalability:

- Azure AppServices are auto scalable but have a limitation of 14GB of storage, But in VMs, we have to use VM scale-set which is expensive and complex to configure it

Availability:

- App services and VMs provides multi region availability

Workflow:

- Azure App Services is a PaaS service, that brings about ease in setting up and maintaining a hosted application.
  App Services helps to easily get the app up and running directly from a git repo. It also enables a CI / CD pipeline configuration to make future deployments efficient.
- Azure VMs is a IaaS and involves a lot of effort from the developer to setup the app and to make future deployments.
  The repos have to be moved manually or git setup has to be configured. In this case only the machine is provided and everything else has to be handled by the developer

Costs:

- Azure VMs are only charged based on disk costs when stopped. The Basic VM cost with 1GB storage is estimated at 589 INR / month
- Azure App Services can be expensive since there is no Pay-as-you-go option and charges are made even when an app is not running. The Basic App Service plan with 1.75 GB storage is estimated to be 946 INR / month.

### Conclusion

Based on the current requirements of this Article-CMS project, we can stick with Azure App Services (web app) as we're getting quick setup and deployment (Including CI/CD) from GIT

### Assess app changes that would change your decision. (From App services to VMs)

When a large number of users are using the CMS and there is a high level of activity, an Azure App Service might not provide the necessary computational power. In this case, an Azure VM with higher number of CPUs can prove effective to maintain latency.
