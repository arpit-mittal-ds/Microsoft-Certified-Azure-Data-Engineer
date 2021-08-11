# WHAT IS DEVOPS ?

The standard across the software industry used to be for the **development team (Dev)
to implement services** and for the **operations team (Ops) to deploy them in the production environment and then monitor them.** The thinking behind this was that the
production environment needed to be locked down, and operational concerns like
provisioning machines, configuration, and monitoring required a different set of
skills than the design and development of services. **DevOps, on the other hand, lets
software engineers take charge of the end-to-end process.**


**DEFINITION** 

A DevOps team owns their solution end to end, from requirements
gathering and design through development and testing to deployment, monitoring, and fixing production issues.


**Two major shifts in the industry caused the emergence of DevOps.**

* The first is the broad adoption of agile software development practices, which aim to optimize the
time it takes for software delivery, from requirements to production. 

*  The second major shift is the move to the cloud. . The key change is the move from individual servers, which
require a lot of maintenance and attention, to infrastructure that can be provisioned
and deprovisioned on demand. 

The shift to the cloud created a renewed focus on automation for deployment and
configuration, which is an invaluable tool in the DevOps toolbox. The infrastructureas-code process of managing and provisioning infrastructure makes deployment and
operational concerns much more like software development. 

**Some of the key software tools that enable DevOps follow:**

* Source code management
* Build automation
* Packaging
* Release automation
* Monitoring and alerting

**BENEFIT**
We store our configuration in DevOps Repos (Git) and deploy using a pipeline.
If needed, we can replicate the deployment in a different environment.


It might seem like a lot of extra effort, but we know from software engineering the
value of automation. It might be easier to, for example, test some code manually once
or twice, but with a small investment in test automation, we save a lot of time in the
long run. We can run tests much more frequently and catch issues as early as they
appear, and that ends up saving us a lot of manual testing time.

DevOps removes
the coordination overhead between the two teams and the issues this overhead produces. For example, a deployment fails and the developer says, “It works on my
machine.” Then the developer works with the ops counterpart to identify the issue.

## DEPLOYING INFRASTRUCTURE




## AZURE DEVOPS

* Azure Pipelines, which we will use to automate build, validation, and deployment

* Source control, also known as Azure Repos, which includes Git hosting, code
review, and policies.

![image](https://user-images.githubusercontent.com/68102477/128985454-9dbb0664-50c8-41c0-9e47-c3d21a4a48be.png)

![image](https://user-images.githubusercontent.com/68102477/128985500-d38beabf-6eeb-463a-aa91-0fa7b00ec3bd.png)

![image](https://user-images.githubusercontent.com/68102477/128985583-cb9c23f0-5e21-4e88-bd1b-0d6cd8acb449.png)

![image](https://user-images.githubusercontent.com/68102477/128985607-73c445a0-8461-4fa5-bb6e-d6992d7fe8a8.png)

### Authenticate against your tenant so that the DevOps service is provisioned under your Azure account


![image](https://user-images.githubusercontent.com/68102477/129005072-48816076-816a-4a44-b273-dc2e3e6fa118.png)




