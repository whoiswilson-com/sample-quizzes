---
title: "AZ-305 — Azure Solutions Architect"
tags: [azure, az-305, architect, design]
note: "Sample study questions — not affiliated with or sourced from Microsoft certification exams"
---

##### Question q001
type: single_choice
correct: [c]

A company needs to design a solution that stores documents uploaded by users. The documents must remain available even if an entire Azure region goes offline. Which storage redundancy option should the architect recommend?

A. Locally redundant storage (LRS)
B. Zone-redundant storage (ZRS)
C. Geo-redundant storage with read access (RA-GRS)
D. Premium SSD managed disk

###### Explanation
RA-GRS replicates data asynchronously to a secondary region hundreds of kilometres away and provides read access to the secondary copy. If the primary region fails, the data is still accessible from the secondary. LRS and ZRS only protect within a single region. Managed disks are block storage for VMs, not document storage.

---

##### Question q002
type: multi_choice
correct: [b, d]

A solution architect is designing an application that processes orders. The ordering API must handle unpredictable traffic spikes without losing any orders. Which TWO components should be included in the design? (Select two.)

A. Azure Traffic Manager
B. Azure Service Bus queue
C. Azure Front Door
D. Azure Functions with queue trigger
E. Azure Bastion

###### Explanation
A Service Bus queue acts as a buffer — the API writes orders to the queue and they're never lost, even during traffic spikes. Azure Functions with a queue trigger processes the messages asynchronously at a sustainable rate. Traffic Manager and Front Door are load balancing and routing services that don't provide message buffering. Bastion is for secure VM access.

---

##### Question q003
type: single_choice
correct: [a]

An organisation requires that all Azure resources are deployed only to the West Europe and North Europe regions. No exceptions should be allowed, regardless of the user's role. What should the architect recommend?

A. Azure Policy with an allowed locations policy
B. Azure RBAC custom role that excludes other regions
C. A management group with a naming convention
D. Azure Advisor recommendations

###### Explanation
Azure Policy can enforce allowed locations at the subscription or management group level. Any deployment to a non-allowed region is denied automatically, regardless of the user's RBAC role. RBAC controls what actions a user can take, but it cannot restrict which regions resources are deployed to. Advisor provides recommendations but does not enforce them.

---

##### Question q004
type: single_choice
correct: [d]

A company is migrating a legacy application that requires a Windows Server with specific third-party drivers installed. The application cannot be containerised. Which Azure compute option should the architect recommend?

A. Azure App Service
B. Azure Kubernetes Service
C. Azure Functions
D. Azure Virtual Machines

###### Explanation
Azure VMs provide full control over the operating system, allowing installation of custom drivers and legacy software. App Service, AKS, and Functions are all PaaS/serverless options that abstract away the OS — you cannot install custom drivers on them. VMs are the right choice when you need OS-level control.

---

##### Question q005
type: multi_choice
correct: [a, c, e]

A solution architect is designing a highly available web application. Which THREE design principles should be applied? (Select three.)

A. Deploy across multiple Availability Zones
B. Use a single large VM instead of multiple smaller VMs
C. Implement health probes on the load balancer
D. Store session state on the web server's local disk
E. Use a managed database service with automatic failover
F. Disable automatic scaling to maintain consistent performance

###### Explanation
High availability requires: spreading resources across Availability Zones (survives data centre failure), health probes to detect and route around failed instances, and managed database services with automatic failover (e.g. Azure SQL with auto-failover groups). A single large VM is a single point of failure. Local session state breaks when traffic moves between instances. Disabling auto-scaling means the app cannot respond to demand changes.

---

##### Question q006
type: single_choice
correct: [b]

An architect is designing identity for a customer-facing mobile application. Customers must be able to sign up with their email address or social accounts (Google, Facebook). Which Azure service should be used?

A. Azure Active Directory (Azure AD)
B. Azure AD B2C (Entra External ID)
C. Azure AD B2B
D. Active Directory Domain Services

###### Explanation
Azure AD B2C (now Entra External ID) is designed for consumer-facing identity — it supports self-service sign-up, social identity providers, and custom branding. Azure AD is for organisational identities. B2B is for inviting external business users into your Azure AD. AD DS is for domain-joined on-premises or VM workloads.

---

##### Question q007
type: sequence
correct: [c, a, d, b]

Place the following steps in the correct order when designing a disaster recovery strategy for an Azure SQL Database.

A. Configure active geo-replication to a secondary region
B. Test failover and validate application connectivity to the secondary
C. Define the Recovery Point Objective (RPO) and Recovery Time Objective (RTO)
D. Set up a failover group with automatic failover policy

###### Explanation
Start by defining your RPO and RTO — these business requirements drive all technical decisions. Then configure geo-replication to a paired region. Set up a failover group to automate the failover process and manage DNS endpoints. Finally, test the failover to ensure the application reconnects correctly and meets the defined RTO.

---

##### Question q008
type: single_choice
correct: [c]

A company stores sensitive customer data in Azure Blob Storage. Regulatory requirements mandate that the data is encrypted with keys managed by the company, not Microsoft. What should the architect recommend?

A. Enable Azure Storage Service Encryption with Microsoft-managed keys
B. Encrypt files client-side before uploading
C. Configure customer-managed keys (CMK) using Azure Key Vault
D. Enable Azure Disk Encryption on the storage account

###### Explanation
Customer-managed keys (CMK) stored in Azure Key Vault give the company full control over the encryption keys while still using Azure's server-side encryption. Microsoft-managed keys are the default but don't meet the requirement for company-managed keys. Client-side encryption works but adds complexity and isn't necessary when CMK is available. Disk Encryption applies to VM disks, not Blob Storage.

---

##### Question q009
type: true_false
correct: [b]

Azure Traffic Manager performs health checks at the application layer (HTTP/HTTPS) by default and can route traffic based on URL path.

A. True
B. False

###### Explanation
Azure Traffic Manager operates at the DNS level, not the application layer. It directs clients to different endpoints based on DNS resolution using routing methods like priority, weighted, or geographic. It performs health checks via HTTP/HTTPS/TCP, but it does not inspect or route based on URL paths. For URL path-based routing, use Azure Application Gateway or Azure Front Door.

---

##### Question q010
type: single_choice
correct: [a]

An architect needs to design a solution where multiple microservices communicate asynchronously. Messages must be processed in the exact order they are sent, and each message must be processed exactly once. Which service should they use?

A. Azure Service Bus with sessions enabled
B. Azure Event Grid
C. Azure Event Hubs
D. Azure Queue Storage

###### Explanation
Azure Service Bus with sessions guarantees FIFO (first-in, first-out) ordering and exactly-once processing within a session. Event Grid is for event-driven reactive programming (at-least-once delivery). Event Hubs is for high-throughput telemetry streaming. Azure Queue Storage provides basic queuing but does not guarantee ordering or exactly-once processing.

---

##### Question q011
type: multi_choice
correct: [b, d]

A company is designing a solution that must meet a 99.99% availability SLA. Which TWO architectural decisions help achieve this? (Select two.)

A. Deploy all resources to a single Availability Zone with premium storage
B. Deploy the application across two or more Azure regions with Azure Front Door
C. Use a single Azure SQL Database with locally redundant backups
D. Implement active-active deployment with automatic failover
E. Schedule nightly VM restarts to ensure clean state

###### Explanation
99.99% availability (about 52 minutes downtime per year) typically requires multi-region deployment with automatic failover — a single-region deployment cannot achieve this SLA regardless of the number of Availability Zones. Azure Front Door provides global load balancing across regions. Active-active deployment means both regions serve traffic, with automatic failover if one fails. A single SQL Database and nightly restarts introduce single points of failure.

---

##### Question q012
type: single_choice
correct: [d]

An architect is designing a data pipeline that ingests millions of IoT telemetry events per second. The data must be available for real-time dashboards and later for batch analytics. Which ingestion service should they recommend?

A. Azure Service Bus
B. Azure Queue Storage
C. Azure Logic Apps
D. Azure Event Hubs

###### Explanation
Azure Event Hubs is designed for massive-scale event ingestion — millions of events per second with low latency. It supports both real-time consumers (e.g. Stream Analytics for dashboards) and batch consumers (e.g. capture to storage for later analysis). Service Bus is for transactional messaging, not high-throughput telemetry. Queue Storage is basic and low-throughput. Logic Apps is for workflow orchestration.

---

##### Question q013
type: single_choice
correct: [b]

A company wants to run containerised workloads without managing any underlying infrastructure. The workloads are short-lived batch jobs that run for 10-30 minutes and then terminate. Which service should the architect recommend?

A. Azure Kubernetes Service (AKS)
B. Azure Container Instances (ACI)
C. Azure App Service
D. Azure Virtual Machine Scale Sets

###### Explanation
Azure Container Instances provides serverless containers — no infrastructure to manage, per-second billing, and fast startup. It's ideal for short-lived batch workloads. AKS requires managing a cluster (overkill for simple batch jobs). App Service is for long-running web applications. VM Scale Sets require managing VMs.

---

##### Question q014
type: true_false
correct: [a]

When designing for cost optimisation, reserved instances provide significant discounts over pay-as-you-go pricing in exchange for a one-year or three-year commitment.

A. True
B. False

###### Explanation
Azure Reserved Instances offer up to 72% savings compared to pay-as-you-go pricing for VMs, SQL Database, Cosmos DB, and other services. You commit to a one-year or three-year term. This is ideal for workloads with predictable, steady-state usage. For variable or short-lived workloads, pay-as-you-go or spot instances are more cost-effective.

---

##### Question q015
type: single_choice
correct: [c]

An architect is designing a solution that needs to cache frequently accessed data to reduce database load. The cache must support data structures like sorted sets and hashes, and must be accessible from multiple application instances. What should they recommend?

A. Azure Blob Storage with CDN
B. Azure Table Storage
C. Azure Cache for Redis
D. Azure Cosmos DB with in-memory acceleration

###### Explanation
Azure Cache for Redis provides a fully managed, in-memory data store that supports rich data structures (strings, hashes, lists, sets, sorted sets). It's accessible from any application instance over the network, making it perfect for shared caching. Blob Storage with CDN caches static files, not application data. Table Storage is persistent NoSQL, not an in-memory cache. Cosmos DB is a database, not a caching layer.

---

##### Question q016
type: multi_choice
correct: [a, c]

An architect must ensure that API keys and connection strings used by an application are stored securely and never appear in source code or configuration files. Which TWO services should be used together? (Select two.)

A. Azure Key Vault
B. Azure Policy
C. Managed Identity
D. Azure Advisor
E. Network Security Group

###### Explanation
Azure Key Vault stores secrets securely (encrypted at rest, access-controlled). Managed Identity lets the application authenticate to Key Vault without needing credentials — the identity is managed by Azure and never exposed in code. Together, they eliminate secrets from source code and config files entirely. Policy enforces rules, Advisor gives recommendations, and NSGs control network traffic — none of them store or retrieve secrets.

---

##### Question q017
type: sequence
correct: [b, d, a, c]

Place the following steps in the correct order when designing a migration from on-premises SQL Server to Azure SQL Database.

A. Perform the data migration using Azure Database Migration Service
B. Assess the on-premises database for compatibility issues using Data Migration Assistant
C. Validate application functionality against the migrated database and cut over
D. Remediate any compatibility issues identified in the assessment

###### Explanation
Start with assessment — Data Migration Assistant identifies T-SQL compatibility issues, deprecated features, and breaking changes. Fix those issues before migrating. Then use Azure Database Migration Service for the actual data migration (supports online migration with minimal downtime). Finally, validate that the application works correctly against the new Azure SQL Database before cutting over production traffic.

---

##### Question q018
type: single_choice
correct: [a]

A company needs to expose internal APIs to external partners with rate limiting, authentication, and usage analytics. Which Azure service should the architect recommend?

A. Azure API Management
B. Azure Application Gateway
C. Azure Front Door
D. Azure Load Balancer

###### Explanation
Azure API Management is a full API gateway — it provides rate limiting (throttling policies), authentication (OAuth2, API keys, certificates), usage analytics, developer portal, and API versioning. Application Gateway is a web traffic load balancer with WAF. Front Door is a global CDN and load balancer. Load Balancer operates at layer 4 (TCP/UDP) with no API-level features.

---

##### Question q019
type: single_choice
correct: [d]

An architect is designing a globally distributed application where users on every continent need sub-10ms read latency. The data model is flexible and includes JSON documents. Which database service should they recommend?

A. Azure SQL Database with geo-replication
B. Azure Database for PostgreSQL — Flexible Server
C. Azure Cache for Redis
D. Azure Cosmos DB with multi-region writes

###### Explanation
Azure Cosmos DB offers guaranteed single-digit millisecond reads at the 99th percentile globally, with turnkey multi-region distribution and multi-region writes. It natively supports JSON documents. SQL Database and PostgreSQL can geo-replicate but don't guarantee sub-10ms reads globally. Redis provides low latency but is a cache, not a primary database for documents.

---

##### Question q020
type: multi_choice
correct: [a, d]

An architect is designing network security for a web application in Azure. Which TWO services work together to protect the application from common web exploits and DDoS attacks? (Select two.)

A. Azure Web Application Firewall (WAF)
B. Azure Bastion
C. Azure Private Link
D. Azure DDoS Protection Standard
E. Azure Key Vault

###### Explanation
WAF (deployed on Application Gateway or Front Door) protects against common web exploits like SQL injection, XSS, and other OWASP top 10 threats. DDoS Protection Standard provides enhanced DDoS mitigation with traffic monitoring, automatic attack detection, and mitigation policies. Together they form a comprehensive protection layer. Bastion is for secure VM management access. Private Link provides private connectivity to services. Key Vault stores secrets.
