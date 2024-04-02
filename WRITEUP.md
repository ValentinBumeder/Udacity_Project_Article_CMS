# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
Costs: 
The costs for hosting applications on VMs are basically higher than hosting on Azure App Services. To ensure availability and performance of applications on VMs you might have to use multiple VMs in VM groups, which lead to higher costs. 
For deploying the app in this course and not as a production use case, you can even use one free Azure App Service, while using a VM leads to costs, which are also very low for VMs with low hardware specifications.

Scalability: 
For Azure App Services, you can use auto-scaling to scale the application, based on the usage in real-time. This happens by scaling up subscriptions, following a App Service Plan. 
The scalability of Azure App Service Instances is limited to 14 GB of memory and 4 vCPU cores. For applications with the demand of very high processing power and lots of users, the Azure App Service it might be necessary to use VMs for scaling over the limits of Azure App Services. 
With VMs, the scaling is a little more complicated. For scaling them, Virtual Machine Scale Sets or Load Balancers can be used. These use multiple VMs in VM groups. Setting up scaling for VMs is more complicated and more effort for the developer, but does not have limits, like the Azure App Service does.

Availability: 
App Services provide a very high availability for applications. The SLAs for production App Services are 99.95%. Furthermore, the effort for maintaining Azure App Services for a developer is very low. 
A high availability of VMs can be reached by using multiple VMs in VM groups. By using multiple VMs, the costs for running an application might be higher, than for a Azure App Service. 
Additionally, the developer has to maintain the VMs by applying patches and keeping the OS up to date to ensure a high availability and security for the VMs.

Workflow:
For deploying an application to a VM, the developer has to do some manual steps. First of, he has to create a VM in Azure and copy the application from his local machine to the VM. For the Flask Application, a developer has to manually install virtual environment and NGINX. Afterwards NGINx has to be configured to redirect incoming connections to the application. Before starting the application, the necessary packages need to be installed. 
Using an Azure App Service, many of the described deployment steps are done automatically by the App Service. As developer, you only have to create a Azure App Service and connect for example the GitHub project of the application, for a automatic deployment of the application. The application can than also be updated automatically, while for a VM, you would have to manually update the application on the VM or build a automated workflow for that. 


- *Choose the appropriate solution (VM or App Service) for deploying the app*
For the article CMS application I would choose a Azure App Service.

- *Justify your choice*
Since the article CMS application doesn't need lots of CPU power or memory and is not expected to have lots of users in the beginning, the limits of Azure App Service will not be reached in my opionion. Furthermore it is a lot easier to deploy the application using an Azure App Service as described under the point Workflow. Additionally, article CMS application does not have special needs regarding the OS or the hardware, so the standard solutions of Azure App Services fit very well for that. Lastly, for the purpose of this course the Azure App Service can be used completly free.

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 
To change my opinion, the requirement of the application for computing power or the load on the system, due to very high usage would have to increase drastically. For example if the application would use AI to manage articles or edit the pictures would demand a lot more computing power. That might lead to performance issues if the usage of the application is high. Then the performance of an Azure App Service could get bad and I would use VMs for scaling the application further up. 
Also, if the system would have very high security requirements, I would use VMs, since you are free to configure VMs a lot more in detail than App Services and you could maybe apply a better security to your application. 
