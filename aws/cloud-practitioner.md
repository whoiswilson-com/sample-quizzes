---
title: "AWS Cloud Practitioner — Cloud Concepts & Core Services"
tags: [aws, cloud-practitioner, clf-c02, fundamentals]
note: "Sample study questions — not affiliated with or sourced from AWS certification exams"
---

##### Question q001
type: single_choice
correct: [b]

A startup wants to launch a web application without purchasing any physical hardware. They want to pay only for the resources they consume. Which cloud computing benefit does this describe?

A. Fault tolerance
B. Pay-as-you-go pricing
C. Elasticity
D. Global reach

###### Explanation
Pay-as-you-go (or on-demand) pricing is a core economic benefit of cloud computing — no upfront hardware investment, you pay for what you use. Elasticity is about scaling resources. Fault tolerance is about surviving failures. Global reach refers to deploying across regions.

---

##### Question q002
type: single_choice
correct: [c]

Which AWS service provides scalable object storage designed for storing and retrieving any amount of data from anywhere on the internet?

A. Amazon EBS
B. Amazon EFS
C. Amazon S3
D. AWS Storage Gateway

###### Explanation
Amazon S3 (Simple Storage Service) is object storage — it stores files as objects in buckets with virtually unlimited capacity. EBS provides block storage volumes for EC2 instances. EFS provides managed file storage (NFS). Storage Gateway is a hybrid storage service that connects on-premises environments to AWS storage.

---

##### Question q003
type: multi_choice
correct: [a, d]

Which TWO of the following are responsibilities of the customer under the AWS Shared Responsibility Model? (Select two.)

A. Managing IAM users and their permissions
B. Physical security of AWS data centres
C. Patching the hypervisor on EC2 hosts
D. Encrypting sensitive data stored in S3
E. Maintaining the global network infrastructure

###### Explanation
Under the Shared Responsibility Model, AWS manages the security "of" the cloud (physical infrastructure, hypervisors, global network), while the customer manages security "in" the cloud (IAM configuration, data encryption, OS patching on EC2, firewall rules). Managing IAM and encrypting your data are always customer responsibilities.

---

##### Question q004
type: true_false
correct: [a]

An AWS Region consists of multiple Availability Zones, each made up of one or more discrete data centres.

A. True
B. False

###### Explanation
Each AWS Region contains multiple Availability Zones (typically 3 or more). Each AZ consists of one or more data centres with independent power, cooling, and networking. This design enables high availability — deploying across AZs protects against single data centre failures.

---

##### Question q005
type: single_choice
correct: [d]

A company needs to run a relational database in AWS but does not want to manage patching, backups, or the underlying operating system. Which service should they use?

A. Amazon EC2 with a database installed manually
B. Amazon DynamoDB
C. Amazon ElastiCache
D. Amazon RDS

###### Explanation
Amazon RDS (Relational Database Service) is a managed service — AWS handles patching, backups, replication, and OS maintenance. You choose your database engine (MySQL, PostgreSQL, etc.) and focus on your data. EC2 with a database is self-managed (IaaS). DynamoDB is a NoSQL database, not relational. ElastiCache is for in-memory caching.

---

##### Question q006
type: single_choice
correct: [a]

Which AWS service allows you to define and provision infrastructure using code in a declarative template format?

A. AWS CloudFormation
B. AWS CodeDeploy
C. AWS Config
D. AWS Systems Manager

###### Explanation
CloudFormation lets you define your infrastructure as code in JSON or YAML templates. AWS provisions and configures the resources to match your template — it's declarative and repeatable. CodeDeploy automates application deployments. Config tracks resource configuration changes. Systems Manager provides operational tools for managing EC2 instances.

---

##### Question q007
type: multi_choice
correct: [b, c]

Which TWO of the following are benefits of using multiple Availability Zones for an application? (Select two.)

A. Reduced data transfer costs between zones
B. Protection against a single data centre failure
C. Higher availability for your application
D. Automatic compliance with regulatory requirements
E. Lower compute costs compared to a single AZ

###### Explanation
Deploying across multiple AZs means your application survives if one data centre (or AZ) goes down, increasing availability. There is actually a small data transfer cost between AZs, so it doesn't reduce costs. Multi-AZ alone doesn't guarantee compliance — that depends on the specific regulations and your configuration.

---

##### Question q008
type: single_choice
correct: [c]

Which AWS service provides a content delivery network (CDN) that caches content at edge locations around the world to reduce latency for end users?

A. Amazon Route 53
B. AWS Global Accelerator
C. Amazon CloudFront
D. Elastic Load Balancing

###### Explanation
CloudFront is AWS's CDN — it caches static and dynamic content at edge locations worldwide, serving users from the nearest location. Route 53 is DNS. Global Accelerator optimises network paths to your application but doesn't cache content. Elastic Load Balancing distributes traffic across targets within a Region.

---

##### Question q009
type: single_choice
correct: [b]

An administrator wants to grant a developer permission to launch EC2 instances but not terminate them. Which AWS service should they use to configure this?

A. Amazon Cognito
B. AWS Identity and Access Management (IAM)
C. AWS Organizations
D. AWS Shield

###### Explanation
IAM lets you create fine-grained permissions — you can allow ec2:RunInstances while denying ec2:TerminateInstances. Cognito manages user authentication for applications (not AWS resource access). Organizations manages multiple AWS accounts. Shield provides DDoS protection.

---

##### Question q010
type: true_false
correct: [b]

The AWS Free Tier provides unlimited free usage of all AWS services for the first 12 months after account creation.

A. True
B. False

###### Explanation
The Free Tier is not unlimited and does not cover all services. It offers three types of offers: 12-month free (limited quantities of specific services like EC2, S3, RDS), always free (services like Lambda with limited monthly invocations), and short-term trials. Exceeding the free tier limits incurs standard charges.

---

##### Question q011
type: single_choice
correct: [d]

A company needs to run short-lived batch processing jobs that can tolerate interruptions. Which EC2 purchasing option would be the most cost-effective?

A. On-Demand Instances
B. Reserved Instances
C. Dedicated Hosts
D. Spot Instances

###### Explanation
Spot Instances offer up to 90% discount compared to On-Demand pricing, but AWS can reclaim them with 2 minutes notice when capacity is needed. This makes them ideal for fault-tolerant, interruptible workloads like batch processing, data analysis, and CI/CD builds. Reserved Instances suit steady-state workloads. Dedicated Hosts are for licensing or compliance requirements.

---

##### Question q012
type: single_choice
correct: [a]

Which AWS service provides recommendations to help you reduce costs, improve performance, and address security gaps in your AWS environment?

A. AWS Trusted Advisor
B. AWS CloudTrail
C. Amazon Inspector
D. AWS Cost Explorer

###### Explanation
Trusted Advisor inspects your AWS environment and provides recommendations across five categories: cost optimisation, performance, security, fault tolerance, and service limits. CloudTrail logs API activity. Inspector assesses EC2 and container workloads for vulnerabilities. Cost Explorer visualises and analyses spending but doesn't provide cross-category recommendations.

---

##### Question q013
type: multi_choice
correct: [a, c, e]

Which THREE of the following are pillars of the AWS Well-Architected Framework? (Select three.)

A. Operational Excellence
B. Elasticity
C. Security
D. Scalability
E. Cost Optimisation

###### Explanation
The six pillars of the Well-Architected Framework are: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimisation, and Sustainability. Elasticity and scalability are cloud concepts but not named pillars of the framework.

---

##### Question q014
type: single_choice
correct: [c]

Which AWS service records all API calls made in your account, including who made the call, when, and from which IP address?

A. Amazon CloudWatch
B. AWS Config
C. AWS CloudTrail
D. AWS X-Ray

###### Explanation
CloudTrail logs every API call made to your AWS account — who called what, when, from where, and whether it succeeded. This is essential for auditing and compliance. CloudWatch monitors metrics and logs. Config tracks resource configuration history. X-Ray traces application requests for debugging.

---

##### Question q015
type: single_choice
correct: [b]

A company wants to consolidate billing for multiple AWS accounts and apply service control policies across all of them. Which service should they use?

A. AWS IAM
B. AWS Organizations
C. AWS Control Tower
D. AWS Budgets

###### Explanation
AWS Organizations lets you centrally manage multiple AWS accounts — consolidated billing, service control policies (SCPs) to restrict what accounts can do, and organisational units (OUs) for grouping accounts. IAM manages users within a single account. Control Tower builds on top of Organizations to automate multi-account setup. Budgets tracks spending but doesn't manage accounts.

---

##### Question q016
type: true_false
correct: [a]

Amazon VPC allows you to launch AWS resources into a logically isolated virtual network that you define.

A. True
B. False

###### Explanation
A Virtual Private Cloud (VPC) is a logically isolated section of the AWS cloud where you define your own network — IP ranges, subnets, route tables, and gateways. Resources like EC2 instances and RDS databases launch into your VPC, giving you control over the network environment.

---

##### Question q017
type: single_choice
correct: [d]

Which AWS support plan provides access to a Technical Account Manager (TAM)?

A. Basic
B. Developer
C. Business
D. Enterprise

###### Explanation
Only the Enterprise support plan includes a designated Technical Account Manager. The TAM provides proactive guidance, architectural reviews, and helps coordinate AWS support. Basic is free with limited support. Developer provides business-hours email support. Business adds 24/7 phone support and faster response times but no TAM.

---

##### Question q018
type: sequence
correct: [c, d, a, b]

Place the following steps in the correct order to deploy a highly available web application on AWS.

A. Configure an Auto Scaling group to maintain the desired number of instances
B. Test failover by terminating an instance and verifying replacement
C. Create a VPC with subnets in at least two Availability Zones
D. Launch EC2 instances and place an Application Load Balancer in front of them

###### Explanation
First set up the network foundation — a VPC with subnets across multiple AZs. Then launch the EC2 instances and an ALB to distribute traffic. Add Auto Scaling to automatically replace failed instances and handle demand changes. Finally test that failover works by terminating an instance and confirming the Auto Scaling group replaces it.

---

##### Question q019
type: single_choice
correct: [a]

Which AWS service is a fully managed NoSQL database that provides single-digit millisecond performance at any scale?

A. Amazon DynamoDB
B. Amazon RDS
C. Amazon Redshift
D. Amazon Aurora

###### Explanation
DynamoDB is AWS's managed NoSQL (key-value and document) database, designed for consistent low-latency performance regardless of scale. RDS and Aurora are relational database services. Redshift is a data warehouse for analytics workloads, not transactional NoSQL.

---

##### Question q020
type: multi_choice
correct: [b, d]

Which TWO of the following are features of Amazon S3? (Select two.)

A. Block-level storage attached to EC2 instances
B. Lifecycle policies to automatically transition objects between storage classes
C. POSIX-compliant file system access
D. Versioning to preserve and recover every version of every object
E. Sub-millisecond latency for all read operations

###### Explanation
S3 supports lifecycle policies (automatically move objects from Standard to Glacier, for example) and versioning (keep every version of an object, enabling recovery from accidental deletes). Block-level storage is EBS. POSIX file system access is EFS. S3 latency is typically single-digit milliseconds, not sub-millisecond.
