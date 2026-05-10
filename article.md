---
author: "Kyle Jones"
date_published: "November 7, 2024"
date_exported_from_medium: "November 10, 2025"
canonical_link: "https://medium.com/@kyle-t-jones/balancing-agility-and-control-in-multi-account-environments-in-aws-2024-update-11fbbe87a6ad"
---

# Balancing agility and control in multi-account environments in AWS (2024 Update) This document presents the design considerations for scaling a
multi-account platform adoption while balancing compliance and flexibility...

### Balancing agility and control in multi-account environments in AWS (2024 Update)
This document presents the design considerations for scaling a multi-account platform adoption while balancing compliance and flexibility. The scenarios in this document are aimed at large enterprises with a strong Central IT team that are transitioning to the cloud. Born in the cloud companies may have a different set of challenges and solutions than those mentioned in this document. This document is aimed at AWS Solution Architects, Cloud Security Architects and Product Owners responsible for defining the capability and feature roadmap for the multi-account platform.

Background and Context:

Multi-Account Environments enable large scale adoption of AWS services and drive business outcomes in an organization, when implemented right. A multi-account platform implementation should be approached as a journey and not as a destination. This is because multi-account platform is a product that evolves with business needs. And because needs are often conflicting and vary by business, workloads, operating model, and skills levels of developers, a one-size fits all approach restricts the platform adoption.

Multi-account environments balance the opposing needs to the two key personas: Central IT team and builder teams. This causes an inherent tension in the implementation. The Central IT team wants consistent and centralized compliance policies enforced on the workloads, this derives from the central team's need to ensure compliance. The workload owners want agility and flexibility in applying the changes to their workloads, dependencies on the platform team slows them down. Compliance is essential, however compliance should not be designed to make the platform unusable. Compliance controls reduce business risk, they should be designed as handrails allowing builders to focus on innovation. A well-designed multi-account platform balances the needs of the stakeholders with an architecture that allows balancing compliance and flexibility and continuously grow to offer additional capabilities.

#### Balanced design for multi-account environments
Builders are the customer of the multi-account environments. Their objective is to get quality solutions and products out to their clients at accelerated speed. Aligning design decisions to the outcome of accelerating builder productivity ensures the platform is designed for adoption by the builders.

While builders are the customers of the multi-account environment, they have varying profiles and often different expectations from the platform. For example: Some builder teams benefit from handrails and need building blocks, others find it more efficient to stand up their workload from scratch. An effective multi-account environment enables multiple tenants to effectively leverage the platform for their goals. The platform tenants have varying needs for 1/Security guardrails, 2/Network connectivity requirements, 3/Identity and RBAC, 4/Accelerators. A well-architected multi-account platform offers reusable components/accelerators without forcing end users into a monolithic architecture pattern. This allows the builders to design their workload's architecture while using platform components and accelerators to speed up implementation. This model also allows increasing collaboration within the enterprise by allowing developers to contribute design patterns and accelerators for consumption by the enterprise.

Design tenets for an effective multi-account platform design (2024 Update):

- Design for user experience and developer productivity
- Implement fit-for-purpose design with modular, composable architecture
- Implement everything as code, emphasizing infrastructure as code (IaC) and policy as code
- Automate end-to-end operations, security detection, and remediation
- Adopt a minimum security baseline, apply security controls as components
- Democratize capability curation and sharing through internal marketplaces
- Embrace GitOps practices for infrastructure and policy management
- Implement continuous compliance and security posture management

Capabilities for a multi-account platform (2024 Update):

A multi-account environment should offer a range of capabilities and avoid a one size fits all model. While one may argue that architecture teams do not have complete visibility into the evolving end user requirements, the patterns that builders and workloads need fit into standard design patterns. The patterns to consider are:1/Based on hosting pattern of end user workloads --- Hosted Workloads, Cloud Native Development Workloads, 2/Functional design of the end user workload, 3/Network connectivity patterns --- Internet Connectivity, On-Premises Connectivity, 4/Security Compliance Framework based on workload risk profile, 5/Shared service approach --- Platform level shared services, Team level shared services.

A well architected multi-account environment offers:\
1. Flexible Account Provisioning:\
--- Multiple account factory products using AWS Control Tower and custom AWS Service Catalog products\ --- Account Factory for Terraform (AFT) for Terraform-based account customization\
2. Identity and Access Management:\
--- Centralized identity management with AWS IAM Identity Center\ --- Fine-grained permissions and attribute-based access control (ABAC) for scalable access management\
3. Network Connectivity and Security:\
--- Centralized network management using AWS Transit Gateway and AWS Network Firewall\ --- VPC designs supporting various connectivity patterns (internet-facing, hybrid, isolated)\
4. Security and Compliance:\
--- Layered security controls using AWS Organizations SCPs, AWS Control Tower guardrails, and AWS Config rules\ --- AWS Security Hub with custom insights for tailored security monitoring\
5. Data Governance:\
--- Centralized data access control across accounts using AWS Lake Formation\ --- Cross-account backup and disaster recovery strategies with AWS Backup\
6. Developer Enablement:\
--- Self-service infrastructure provisioning through AWS Service Catalog and AWS Proton\ --- CI/CD pipelines as a service using AWS CodePipeline and AWS Proton\
7. Observability and Management:\
--- Centralized logging and monitoring using AWS CloudWatch and AWS OpenSearch Service\ --- Cross-account resource management with AWS Systems Manager\
8. Cost Management:\
--- Organization-wide cost management using AWS Cost Explorer and AWS Budgets\ --- Tagging strategies enforced through AWS Organizations tag policies

Practices to implement a compliant design with flexibility

The multi-account framework provides the broad principles for a flexible and compliant design. The following section dives deep into the implementation details of the multi-account framework, that align to these capabilities.

1.  [Offer a flexible yet compliant account with fit for purpose security framework:]

- Segregate environments with AWS Organizations: Implement a small number of AWS Organizations, setting up additional instances for independently governed subsidiaries. Use AWS Organizations AI Service Opt-out Policies to control AI/ML service usage across accounts.
- Multiple Account Factory Products: Offer account factory products with different levels of handrails using AWS Control Tower and custom AWS Service Catalog products. Implement Account Factory for Terraform (AFT) for Terraform-based account customization.
- OU Design for flexible controls: Leverage OU segregation and nested OUs to create a compliant yet flexible control framework. Layer Service Control Policies (SCPs) with nested OUs to accommodate multiple workloads with differing control requirements.
- Layer configurations over the minimal security baseline: Create a model with minimal security baseline and build security guardrails as opt-in layers. Use a mix of preventive and detective control strategies, leveraging AWS Control Tower Guardrails, AWS Security Hub, AWS Config Rules, and AWS Lambda automation.
- Guardrail strategy: Define a guardrail implementation strategy using a blend of preventive and detective approaches. Use SCPs, AWS Service Catalog, and infrastructure as code (IaC) checks in deployment pipelines.
- Centralized configuration: Use AWS Control Tower, AWS Security Hub, AWS Config conformance packs, AWS Firewall Manager, and AWS Network Firewall to apply configuration controls centrally.
- Fine-grained access management: Implement least privilege access using IAM Roles and policies. Use IAM permissions boundaries and AWS IAM Identity Center for secure delegation of privileges and fine-grained access control.

2\. Increase end user agility and reduce platform operating costs:

- Fully automate account provisioning and management: Integrate AWS Service Catalog with ITSM systems and use AWS Control Tower, AWS Step Functions, and AWS Lambda for end-to-end automation.
- Automate reporting consolidation: Use AWS Security Hub, AWS Systems Manager, AWS CloudWatch, and AWS Audit Manager for automated compliance and operational reporting.
- Eliminate undifferentiated heavy lifting: Offer and automate platform-level services like AWS Backup for centralized backup management.
- Consume well-architected resource patterns: Build a catalog of best practice configurations using AWS Service Catalog and share reusable IaC components through central code repos.
- DevOps as a Service: Offer application orchestration, deployment automation, logging, monitoring, and CI/CD capabilities using AWS developer tools and management services.

3\. Build discovery, compliance and reporting into the platform:

- Automated detection and remediation: Use AWS Security Hub Response and Remediation solution, AWS Config conformance packs, and create additional playbooks using AWS CloudWatch Events, AWS Lambda, AWS Step Functions, and AWS Systems Manager.
- Central compliance monitoring: Configure central dashboards in AWS Control Tower and AWS Security Hub. Enable specific security standards and use AWS Security Hub's custom insights feature for tailored security analytics.
- Tagging Governance: Enforce tagging governance using AWS Organizations tag policies, AWS Service Catalog, and Tag Options feature.

New Considerations for 2024:

- Implement AWS Proton for standardized infrastructure and CI/CD pipeline provisioning across accounts.
- Utilize AWS Resource Explorer for cross-account resource discovery and management.
- Implement AWS Lake Formation for centralized data lake governance across accounts.
- Embrace GitOps practices for infrastructure and policy management, using tools like AWS CodeCommit or integrating with GitHub.
- Implement continuous compliance and security posture management using AWS Security Hub and AWS Config.
- Utilize AWS CloudFormation StackSets for organization-wide resource deployment and management.
- Implement cross-account resource sharing using AWS RAM (Resource Access Manager) for shared services.

Summary: A successful multi-account architecture blends compliance and flexibility to allow builders to build fast. Building the multi-account environment as an amalgamation of capabilities as atomic components and services assures that multiple teams and workloads needing differing capabilities are able to adopt the platform. By leveraging the latest AWS services and features, organizations can create a flexible, secure, and scalable multi-account environment that accelerates innovation while ensuring compliance.

References\ [https://aws.amazon.com/blogs/mt/introducing-aws-config-conformance-packs/](https://aws.amazon.com/blogs/mt/introducing-aws-config-conformance-packs/)

[https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html)

[https://docs.aws.amazon.com/aws-backup/latest/devguide/manage-cross-account.html](https://docs.aws.amazon.com/aws-backup/latest/devguide/manage-cross-account.html)

[https://aws.amazon.com/network-firewall/](https://aws.amazon.com/network-firewall/)

[https://aws.amazon.com/firewall-manager/](https://aws.amazon.com/firewall-manager/)

[https://aws.amazon.com/servicecatalog/](https://aws.amazon.com/servicecatalog/)

[https://aws.amazon.com/blogs/mt/best-practices-for-organizational-units-with-aws-organizations/](https://aws.amazon.com/blogs/mt/best-practices-for-organizational-units-with-aws-organizations/)

[https://aws.amazon.com/audit-manager/](https://aws.amazon.com/audit-manager/)

[https://aws.amazon.com/blogs/mt/introducing-aws-config-conformance-packs/](https://aws.amazon.com/blogs/mt/introducing-aws-config-conformance-packs/)

[https://aws.amazon.com/blogs/security/automated-response-and-remediation-with-aws-security-hub/](https://aws.amazon.com/blogs/security/automated-response-and-remediation-with-aws-security-hub/)

[https://aws.amazon.com/blogs/security/delegate-permission-management-to-developers-using-iam-permissions-boundaries/](https://aws.amazon.com/blogs/security/delegate-permission-management-to-developers-using-iam-permissions-boundaries/)

[https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-standards-cis.html](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-standards-cis.html)re
