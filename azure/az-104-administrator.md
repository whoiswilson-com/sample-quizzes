---
title: "AZ-104 — Azure Administrator"
tags: [azure, az-104, administrator]
note: "Sample study questions — not affiliated with or sourced from Microsoft certification exams"
---

##### Question q001
type: single_choice
correct: [c]

You need to ensure that a user can manage virtual machines in a specific resource group but cannot modify any other resources in the subscription. What should you do?

A. Assign the Global Administrator role in Azure AD
B. Assign the Contributor role at the subscription level
C. Assign the Virtual Machine Contributor role at the resource group level
D. Assign the Owner role at the resource group level

###### Explanation
Virtual Machine Contributor scoped to the resource group gives exactly the permissions needed — manage VMs in that group only. Subscription-level Contributor is too broad. Owner is too permissive (includes role assignment). Global Administrator is an Azure AD role, not an Azure RBAC role.

---

##### Question q002
type: multi_choice
correct: [b, d]

Which TWO of the following are required when creating a new Azure virtual network? (Select two.)

A. A network security group
B. An address space in CIDR notation
C. A VPN gateway
D. At least one subnet
E. A public IP address

###### Explanation
Every virtual network requires an address space (e.g. 10.0.0.0/16) and at least one subnet. NSGs, VPN gateways, and public IPs are optional and can be added later as needed.

---

##### Question q003
type: single_choice
correct: [a]

A company has a storage account containing sensitive financial data. They need to ensure that all data written to this account is automatically encrypted at rest. What should they configure?

A. No action — Azure Storage Service Encryption is enabled by default for all storage accounts
B. Enable Azure Disk Encryption on the storage account
C. Create an Azure Key Vault and manually encrypt each blob before upload
D. Enable HTTPS-only transfer on the storage account

###### Explanation
Azure Storage Service Encryption (SSE) encrypts all data at rest by default using Microsoft-managed keys. No action is required to enable it. You can optionally switch to customer-managed keys via Key Vault for greater control, but the default already meets the requirement. HTTPS-only protects data in transit, not at rest.

---

##### Question q004
type: single_choice
correct: [d]

You need to allow traffic from the internet to reach a web server running on an Azure VM on port 443. The VM is in a subnet with a network security group attached. What should you create?

A. A user-defined route
B. A service endpoint
C. An application security group
D. An inbound security rule allowing TCP port 443

###### Explanation
NSGs filter traffic using security rules. An inbound rule allowing TCP 443 from the internet (source: Internet or Any) permits HTTPS traffic to reach the VM. A user-defined route changes routing behaviour. A service endpoint secures access to PaaS services. Application security groups help group VMs logically within NSG rules but don't create the allow rule themselves.

---

##### Question q005
type: true_false
correct: [a]

Azure RBAC role assignments are inherited from parent scopes. A role assigned at the subscription level applies to all resource groups and resources within that subscription.

A. True
B. False

###### Explanation
RBAC uses scope inheritance. A role assigned at a management group flows down to subscriptions, then to resource groups, then to individual resources. This is why you should assign roles at the narrowest scope necessary — assigning Contributor at the subscription level gives access to every resource group and resource in it.

---

##### Question q006
type: single_choice
correct: [b]

You have a Linux VM in Azure that is running out of disk space on its OS disk. You need to increase the disk size with minimal downtime. What should you do?

A. Create a new VM with a larger OS disk and migrate the data manually
B. Stop (deallocate) the VM, increase the disk size in the portal, then restart the VM
C. Attach an additional data disk and move the OS to it
D. Change the VM size to one that includes a larger temporary disk

###### Explanation
To resize an OS disk, you must first stop (deallocate) the VM. Then you can increase the disk size through the portal, CLI, or PowerShell. After restarting, you may need to expand the partition within the OS. You cannot shrink a disk — only increase it. The temporary disk is ephemeral and not suitable for persistent data.

---

##### Question q007
type: multi_choice
correct: [a, c, e]

Which THREE of the following can be configured as sources or destinations in a network security group rule? (Select three.)

A. IP address or CIDR range
B. Azure subscription ID
C. Application security group
D. Azure AD group
E. Service tag (e.g. Internet, VirtualNetwork)

###### Explanation
NSG rules support IP addresses/CIDR ranges, application security groups (logical groupings of VMs), and service tags (predefined labels like Internet, AzureLoadBalancer, VirtualNetwork). Azure AD groups and subscription IDs cannot be used in NSG rules — RBAC and NSGs are separate systems.

---

##### Question q008
type: single_choice
correct: [c]

An administrator needs to run a script that creates 50 Azure resources. The script should be idempotent — running it multiple times should produce the same result. Which approach is most appropriate?

A. Azure CLI with imperative commands in a bash script
B. Azure PowerShell with imperative commands
C. An ARM template or Bicep file deployed with az deployment group create
D. Manually creating resources through the Azure portal

###### Explanation
ARM templates and Bicep are declarative and idempotent by design — you define the desired state and Azure ensures it matches, whether you run the deployment once or ten times. Imperative CLI or PowerShell scripts would need custom logic to check for existing resources before creating them. The portal is manual and not repeatable.

---

##### Question q009
type: single_choice
correct: [b]

You need to copy a large number of files from an on-premises file server to Azure Blob Storage. The files total 2 TB and you need the transfer to be as fast as possible. Which tool should you use?

A. Azure Storage Explorer
B. AzCopy
C. Azure Portal upload
D. Azure File Sync

###### Explanation
AzCopy is a command-line tool optimised for high-performance bulk transfers to and from Azure Storage. It supports parallel transfers, resumable copies, and can saturate your network bandwidth. Storage Explorer uses AzCopy under the hood but adds GUI overhead. Portal upload is impractical for 2 TB. File Sync is designed for ongoing synchronisation, not one-time bulk migration.

---

##### Question q010
type: single_choice
correct: [d]

A storage account needs to be accessible only from VMs within a specific virtual network. All other access, including from the internet, must be blocked. What should you configure?

A. A shared access signature with IP restrictions
B. HTTPS-only transfer
C. Azure AD authentication for the storage account
D. Storage account firewall with a virtual network rule and default deny

###### Explanation
The storage account firewall lets you restrict access to specific virtual networks via service endpoints or private endpoints, and set the default action to Deny. This blocks all access except from the allowed networks. SAS tokens can restrict by IP but don't block the public endpoint entirely. HTTPS-only and Azure AD authentication don't control network access.

---

##### Question q011
type: sequence
correct: [c, a, d, b]

Place the following steps in the correct order to configure Azure AD Multi-Factor Authentication for a group of users.

A. Create a Conditional Access policy targeting the user group
B. Test by signing in as a member of the group and completing the MFA prompt
C. Verify that users are registered for MFA methods in their security info
D. Set the policy to require multi-factor authentication as a grant control

###### Explanation
First ensure users have registered MFA methods (otherwise they'll be locked out). Then create the Conditional Access policy, configure it to require MFA as a grant control, and finally test with a member of the targeted group.

---

##### Question q012
type: single_choice
correct: [a]

You need to monitor the CPU usage of all VMs in a resource group and receive an email when any VM exceeds 90% CPU for more than 5 minutes. What should you use?

A. Azure Monitor alert rule with a metric condition
B. Azure Advisor recommendation
C. Azure Service Health notification
D. Activity log alert

###### Explanation
Azure Monitor alert rules let you set metric-based conditions (e.g. CPU > 90% for 5 minutes) scoped to a resource group, and trigger actions like sending email via an action group. Advisor gives recommendations, not real-time alerts. Service Health tracks Azure platform issues. Activity log alerts trigger on management operations (create, delete), not performance metrics.

---

##### Question q013
type: multi_choice
correct: [b, d]

Which TWO of the following are valid Azure Blob Storage access tiers? (Select two.)

A. Standard
B. Hot
C. Warm
D. Archive
E. Premium

###### Explanation
Azure Blob Storage has three access tiers: Hot (frequent access, higher storage cost, lower access cost), Cool (infrequent access, lower storage cost, higher access cost), and Archive (rare access, lowest storage cost, highest retrieval cost and latency). "Standard" and "Premium" describe performance tiers of the storage account, not blob access tiers. "Warm" is not an Azure tier.

---

##### Question q014
type: true_false
correct: [b]

An Azure network security group can be associated with a virtual network.

A. True
B. False

###### Explanation
NSGs can be associated with subnets or individual network interfaces — not with the virtual network itself. To apply an NSG to all traffic in a VNet, you must associate it with each subnet within that VNet.

---

##### Question q015
type: single_choice
correct: [c]

You manage a web application running on Azure App Service. You need to configure the app to automatically scale from 2 to 10 instances when the average CPU usage exceeds 70%. What should you configure?

A. Scale up (increase the App Service plan size)
B. Azure Load Balancer
C. Scale out with an autoscale rule based on CPU metric
D. Azure Traffic Manager

###### Explanation
Scale out (horizontal scaling) adds more instances of your app. An autoscale rule on the App Service plan triggers this based on metrics like CPU usage. Scale up (vertical scaling) increases the size of each instance but doesn't add more. Load Balancer and Traffic Manager distribute traffic but don't control instance count.

---

##### Question q016
type: single_choice
correct: [a]

You need to give a third-party application temporary read access to a specific container in Azure Blob Storage. The access should expire after 24 hours and should not require sharing the storage account keys. What should you use?

A. A shared access signature (SAS) with a 24-hour expiry scoped to the container
B. Azure AD service principal with Storage Blob Data Reader role
C. A storage account access key shared with the third party
D. A managed identity assigned to the third-party application

###### Explanation
A SAS token provides time-limited, scoped access to specific resources without exposing the account keys. You can restrict it to a single container, set it to read-only, and set a 24-hour expiry. Sharing account keys gives full access. Azure AD roles and managed identities are better for long-term access from trusted applications, not temporary third-party access.

---

##### Question q017
type: single_choice
correct: [d]

You are troubleshooting connectivity between two VMs in different Azure virtual networks. The VMs cannot communicate. What is the most likely missing configuration?

A. Both VMs need public IP addresses
B. A network security group rule is blocking traffic
C. The VMs are in different Azure AD tenants
D. Virtual network peering has not been configured between the two VNets

###### Explanation
By default, Azure virtual networks are isolated — VMs in different VNets cannot communicate. Virtual network peering connects two VNets and allows traffic to flow between them. Public IPs would allow internet communication but not private VNet-to-VNet traffic. NSG rules could block traffic, but without peering there is no path for traffic at all. Different Azure AD tenants don't prevent network connectivity.

---

##### Question q018
type: multi_choice
correct: [a, d]

Which TWO of the following tasks require the Owner role and cannot be performed with the Contributor role? (Select two.)

A. Assigning RBAC roles to other users
B. Creating virtual machines
C. Creating and deleting resource groups
D. Creating or modifying Azure Policy assignments at the assigned scope
E. Deploying ARM templates

###### Explanation
The key difference between Owner and Contributor is that Owner can manage access (assign RBAC roles) and manage policy, while Contributor cannot. Both roles can create, modify, and delete resources like VMs, resource groups, and ARM deployments.

---

##### Question q019
type: single_choice
correct: [b]

You need to ensure that no one in your organisation can create virtual machines larger than Standard_D4s_v3 in a specific subscription. What should you use?

A. Azure RBAC custom role
B. Azure Policy
C. Azure Advisor
D. Management group access review

###### Explanation
Azure Policy enforces rules across resources — you can create a policy that restricts allowed VM sizes to specific SKUs. This prevents anyone from deploying non-compliant VMs, regardless of their RBAC role. RBAC controls who can do what, but cannot restrict which SKU sizes are used. Advisor makes recommendations but doesn't enforce them.

---

##### Question q020
type: sequence
correct: [d, b, a, c]

Place the following steps in the correct order to configure a site-to-site VPN connection between an on-premises network and an Azure virtual network.

A. Create the VPN connection and provide the shared key
B. Create the virtual network gateway in Azure
C. Verify the connection status shows as Connected
D. Create a gateway subnet in the Azure virtual network

###### Explanation
First create a dedicated gateway subnet (must be named GatewaySubnet) in the VNet. Then create the virtual network gateway, which deploys into that subnet (this takes 20-45 minutes). Then create the connection resource linking the Azure gateway to the on-premises local network gateway using a shared key. Finally verify the connection status.
