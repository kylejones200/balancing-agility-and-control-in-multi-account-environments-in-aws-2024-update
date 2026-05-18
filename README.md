# Balancing agility and control in multi account environments in AWS 2024 Update

Published: 2024-11-07
Medium: [https://medium.com/@kyle-t-jones/balancing-agility-and-control-in-multi-account-environments-in-aws-2024-update-11fbbe87a6ad](https://medium.com/@kyle-t-jones/balancing-agility-and-control-in-multi-account-environments-in-aws-2024-update-11fbbe87a6ad)

## Business context

This document presents the design considerations for scaling a multi-account platform adoption while balancing compliance and flexibility. The scenarios in this document are aimed at large enterprises with a strong Central IT team that are transitioning to the cloud. Born in the cloud companies may have a different set of challenges and solutions than those mentioned in this document. This document is aimed at AWS Solution Architects, Cloud Security Architects and Product Owners responsible for defining the capability and feature roadmap for the multi-account platform.

Multi-Account Environments enable large scale adoption of AWS services and drive business outcomes in an organization, when implemented right. A multi-account platform implementation should be approached as a journey and not as a destination. This is because multi-account platform is a product that evolves with business needs. And because needs are often conflicting and vary by business, workloads, operating model, and skills levels of developers, a one-size fits all approach restricts the platform adoption.

Multi-account environments balance the opposing needs to the two key personas: Central IT team and builder teams. This causes an inherent tension in the implementation. The Central IT team wants consistent and centralized compliance policies enforced on the workloads, this derives from the central team's need to ensure compliance. The workload owners want agility and flexibility in applying the changes to their workloads, dependencies on the platform team slows them down. Compliance is essential, however compliance should not be designed to make the platform unusable. Compliance controls reduce business risk, they should be designed as handrails allowing builders to focus on innovation. A well-designed multi-account platform balances the needs of the stakeholders with an architecture that allows balancing compliance and flexibility and continuously grow to offer additional capabilities.

## About

Place the code for this article in this repository.
The original article export is saved as `article.md`.

## Files

Add your `.ipynb`, `.py`, `.yaml`, `.js`, `.ts`, or other project files here.

## Disclaimer

Educational/demo code only. Not financial, safety, or engineering advice. Use at your own risk. Verify results independently before any production or operational use.

## License

MIT — see [LICENSE](LICENSE).