# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

APP Service: Low cost, scalable and HA architecture. Low compute capability, good integration via Github Actions, good integration with Active Directory for easy setup.

VM: Lower cost, and allows for more customization of the APP + more possible compute power. If this CMS grows in size and needs optimization, a VM would maybe be better.

Comparing similar machines (2 B2s) an VM costs less than half of an App Service. 

![image](https://user-images.githubusercontent.com/27367589/159196921-d8ef95f7-89ea-4a3f-9f67-78363281669d.png)

As illustrated on this diagram, however, VMs require substantially more management than APP services.
However, they offer more Control and support for Legacy applications, with fine-grained customization of the underlying OS.

![image](https://user-images.githubusercontent.com/27367589/159196976-4f5a9aac-9706-4d10-97e6-939293b42663.png)

As for Workflow, APP service offers more easiness of deploy, integrating directly with Github via Github Actions.

As for scalability, both choices offer good scalability, APP Services with built-in support and VMs with VMSS (VM Scale Sets).

My choice: Due to ease of implementation and deploy, I chose APP service since it supports Python deployments and direct integration with Github Actions.

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

App Service: If the CMS needed more computational power (too many concurrent users, or heavier session control, something like that) the costs could rise quickly. APP Service deployments also can't be as optimized as VMs, so that would generate extra cost.

VM: VMs generate more overhead in Development, the CI/CD cycle isn't as straight forward as developing for App Services. Also, horizontally scaling VMs is significantly more complex than App Services, so if demand grows significantly, it could become very expensive and demanding.
