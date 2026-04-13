---
title: "AZ-900 — Cloud Concepts & Azure Fundamentals"
tags: [azure, az-900, fundamentals, cloud-concepts]
note: "Sample study questions — not affiliated with or sourced from Microsoft certification exams"
---

##### Question q001
type: single_choice
correct: [c]

A company wants to move from owning physical servers to a model where they pay only for the compute resources they actually use each month. Which cloud characteristic does this describe?

A. High availability
B. Elasticity
C. Consumption-based pricing
D. Fault tolerance

###### Explanation
Consumption-based pricing means you pay for what you use — no upfront hardware costs. This is one of the fundamental economic benefits of cloud computing. Elasticity is about scaling resources up and down, which is related but distinct.

---

##### Question q002
type: single_choice
correct: [b]

Which cloud deployment model allows an organisation to keep sensitive data in their own data centre while using cloud services for less sensitive workloads?

A. Public cloud
B. Hybrid cloud
C. Private cloud
D. Community cloud

###### Explanation
A hybrid cloud combines on-premises infrastructure (or a private cloud) with public cloud services. This lets organisations keep sensitive workloads local while leveraging the scalability of the public cloud for everything else.

---

##### Question q003
type: multi_choice
correct: [a, d]

Which TWO of the following are characteristics of a Platform as a Service (PaaS) solution? (Select two.)

A. The cloud provider manages the underlying operating system
B. The customer is responsible for patching the virtual machines
C. The customer deploys and manages the network infrastructure
D. The customer deploys applications without managing the host environment
E. The customer manages the physical hardware

###### Explanation
With PaaS (e.g. Azure App Service), the provider manages the OS, runtime, and infrastructure. You just deploy your application code. VM patching, network infrastructure, and hardware are all the provider's responsibility — those are IaaS or on-premises concerns.

---

##### Question q004
type: true_false
correct: [b]

In a Software as a Service (SaaS) model, the customer is responsible for managing the underlying operating system.

A. True
B. False

###### Explanation
SaaS provides a complete application (e.g. Microsoft 365, Salesforce). The provider manages everything — infrastructure, platform, OS, and the application itself. The customer only manages their data and user access.

---

##### Question q005
type: single_choice
correct: [a]

Which cloud concept describes the ability of a system to automatically increase or decrease resources based on demand?

A. Elasticity
B. Agility
C. Geo-distribution
D. High availability

###### Explanation
Elasticity is the ability to automatically scale resources to match demand — scaling out when traffic spikes and scaling back in when it drops. High availability keeps systems running; agility is about rapid deployment; geo-distribution spreads resources across regions.

---

##### Question q006
type: single_choice
correct: [d]

A company requires that their application remains accessible even if an entire Azure data centre goes offline. What should they implement?

A. A larger virtual machine size
B. Azure Load Balancer within a single region
C. Multiple availability sets
D. Deployment across multiple Azure regions

###### Explanation
An entire data centre failure requires geographic redundancy. Deploying across multiple Azure regions ensures the application survives a regional outage. Availability sets and single-region load balancing protect against failures within a data centre, not across data centres.

---

##### Question q007
type: multi_choice
correct: [b, c]

Which TWO of the following are benefits of cloud computing compared to on-premises infrastructure? (Select two.)

A. Unlimited free bandwidth
B. Ability to scale resources up or down quickly
C. Reduced capital expenditure on hardware
D. Complete elimination of all security responsibilities
E. Guaranteed zero downtime

###### Explanation
Cloud computing offers rapid scalability (provision in minutes, not weeks) and shifts hardware costs from capital expenditure to operational expenditure. It does not provide unlimited bandwidth (you pay for egress), does not eliminate security responsibilities (shared responsibility model), and does not guarantee zero downtime (SLAs offer targets, not absolutes).

---

##### Question q008
type: single_choice
correct: [b]

What is the shared responsibility model in cloud computing?

A. The cloud provider and customer share the cost of all resources equally
B. Security responsibilities are divided between the cloud provider and the customer depending on the service type
C. The cloud provider is solely responsible for all aspects of security
D. The customer is solely responsible for all aspects of security

###### Explanation
The shared responsibility model defines which security tasks the provider handles and which the customer handles. The split varies by service type: with IaaS the customer manages more (OS, apps, data); with SaaS the provider manages most of the stack. The customer is always responsible for their data and access management.

---

##### Question q009
type: single_choice
correct: [c]

Which type of expenditure is typically associated with purchasing physical servers for an on-premises data centre?

A. Operational expenditure (OpEx)
B. Variable expenditure
C. Capital expenditure (CapEx)
D. Recurring expenditure

###### Explanation
Purchasing physical hardware is a capital expenditure — a large upfront investment in assets that depreciate over time. Cloud computing shifts this to operational expenditure (OpEx), where you pay ongoing costs based on usage.

---

##### Question q010
type: true_false
correct: [a]

Azure regions are made up of one or more data centres that are connected with low-latency networking.

A. True
B. False

###### Explanation
An Azure region is a geographical area containing one or more data centres networked together with low-latency connections. When you deploy a resource to a region, Azure places it in one of these data centres.

---

##### Question q011
type: single_choice
correct: [b]

What is an Azure Availability Zone?

A. A grouping of Azure subscriptions for billing purposes
B. A physically separate location within an Azure region with independent power, cooling, and networking
C. A method for replicating data between Azure regions
D. A virtual network that spans multiple regions

###### Explanation
Availability Zones are physically separate data centres within a single Azure region. Each zone has independent power, cooling, and networking. Deploying across zones protects against single data centre failures within that region.

---

##### Question q012
type: single_choice
correct: [a]

Which Azure service provides a managed relational database without requiring you to manage the underlying virtual machine or operating system?

A. Azure SQL Database
B. Azure Virtual Machines with SQL Server installed
C. Azure Blob Storage
D. Azure Virtual Network

###### Explanation
Azure SQL Database is a PaaS offering — Microsoft manages the VM, OS, patching, and backups. You focus on your database and queries. Running SQL Server on a VM (IaaS) means you manage the OS and patching yourself. Blob Storage is for unstructured data, not relational databases.

---

##### Question q013
type: multi_choice
correct: [a, c, d]

Which THREE of the following are core Azure architectural components? (Select three.)

A. Regions
B. Pricing tiers
C. Resource groups
D. Subscriptions
E. Service Level Agreements

###### Explanation
Regions (geographic locations), resource groups (logical containers for resources), and subscriptions (billing and access boundaries) are core architectural components in Azure. Pricing tiers and SLAs are commercial constructs, not architectural ones.

---

##### Question q014
type: single_choice
correct: [d]

An organisation has several departments that each need to track their own Azure spending independently. What should they use?

A. Multiple resource groups within one subscription
B. Azure Cost Management tags only
C. A single subscription with department folders
D. Separate subscriptions for each department

###### Explanation
Separate subscriptions provide clear billing boundaries — each subscription generates its own invoice and can have its own payment method. Resource groups can be tagged for cost tracking, but subscriptions provide the cleanest separation for independent billing. Tags can supplement this but are not a billing boundary on their own.

---

##### Question q015
type: single_choice
correct: [c]

Which tool in the Azure portal provides personalised recommendations to improve the reliability, security, performance, and cost of your Azure resources?

A. Azure Monitor
B. Azure Service Health
C. Azure Advisor
D. Azure Policy

###### Explanation
Azure Advisor analyses your resource configuration and usage, then provides personalised best-practice recommendations across five categories: reliability, security, performance, cost, and operational excellence. Monitor collects metrics and logs; Service Health tracks Azure outages; Policy enforces rules.

---

##### Question q016
type: true_false
correct: [b]

A resource group in Azure can contain resources from only one Azure region.

A. True
B. False

###### Explanation
A resource group is a logical container — it has a location (for metadata storage), but the resources inside it can be in any Azure region. You might have a resource group in UK South containing a VM in East US and a database in West Europe.

---

##### Question q017
type: sequence
correct: [c, a, d, b]

Place the following Azure governance concepts in order from broadest scope to narrowest scope.

A. Subscription
B. Resource
C. Management group
D. Resource group

###### Explanation
The hierarchy from broadest to narrowest is: Management group (can contain multiple subscriptions) → Subscription (billing boundary, contains resource groups) → Resource group (logical container for resources) → Resource (individual service instance like a VM or database).

---

##### Question q018
type: single_choice
correct: [b]

Which Azure service would you use to deploy and manage infrastructure using templates that define your resources in a declarative format?

A. Azure CLI
B. Azure Resource Manager (ARM) templates
C. Azure Cloud Shell
D. Azure Portal

###### Explanation
ARM templates (and their successor, Bicep) let you define infrastructure as code in a declarative JSON or Bicep format. Azure deploys and manages the resources to match your template. The CLI and Portal are tools for interacting with Azure, but they are imperative (you tell them what to do step by step). Cloud Shell is a browser-based terminal.

---

##### Question q019
type: single_choice
correct: [c]

Which Azure service acts as a firewall for Azure SQL Database, Azure Blob Storage, and other services, allowing you to restrict access to specific virtual networks and IP addresses?

A. Azure Active Directory
B. Azure DDoS Protection
C. Service endpoints and private endpoints
D. Azure Front Door

###### Explanation
Service endpoints and private endpoints allow you to restrict access to Azure PaaS services (like SQL Database and Blob Storage) so they are only reachable from specific virtual networks or IP addresses. Azure AD handles identity, DDoS Protection mitigates attacks, and Front Door is a global load balancer and CDN.

---

##### Question q020
type: multi_choice
correct: [a, c]

Which TWO of the following are valid use cases for Azure Functions? (Select two.)

A. Running a piece of code in response to an HTTP request without managing a server
B. Hosting a full Windows desktop application in the cloud
C. Processing messages from a queue automatically as they arrive
D. Replacing Azure Active Directory for identity management
E. Storing large unstructured files like videos and images

###### Explanation
Azure Functions is a serverless compute service — it runs small pieces of code (functions) in response to triggers like HTTP requests, queue messages, timers, and events. It is not designed for hosting desktop applications, managing identity, or storing files (that's Blob Storage).
