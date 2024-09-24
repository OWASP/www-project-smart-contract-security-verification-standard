# Utilizing the SCSVS

The OWASP Smart Contract Security Verification Standard (SCSVS) serves several key purposes:

- **Assisting Development Teams**: Guide smart contract developers in designing, implementing, and maintaining secure decentralized applications (dApps) and contracts, particularly on EVM-based blockchains.

- **Framework for Security Teams**: Assist security professionals in setting requirements, conducting security audits, and performing penetration tests against smart contract systems to ensure they meet robust security standards.

- **Aligning Security Benchmarks**: Establish a common security framework that can be adopted by blockchain platforms, vendors, developers, and clients regarding security expectations in smart contracts and decentralized applications.

## Security Verification Layers

The SCSVS categorizes security verification into three distinct levels, each aimed at different levels of security assurance in smart contract development and deployment:

1. **SCSVS Level 1 - Basic Security**: This level is designed for smart contracts with lower security risks. It focuses on fundamental security controls, ensuring baseline protection for any decentralized application.

2. **SCSVS Level 2 - Moderate Security**: Ideal for smart contracts that handle sensitive data, financial transactions, or are part of a DeFi ecosystem. Level 2 provides a more balanced approach to security, addressing common vulnerabilities like reentrancy attacks, gas inefficiencies, and access control weaknesses.

3. **SCSVS Level 3 - High Assurance Security**: This level is tailored for mission-critical smart contracts where significant financial assets, governance, or high-value transactions are at stake. Level 3 ensures extensive security measures and covers advanced protections such as formal verification, multi-signature wallets, and decentralized governance.

Each level of the SCSVS provides a detailed set of security requirements, mapping these to essential security features and practices needed to build secure smart contracts. Whether developing, auditing, or deploying smart contracts, the SCSVS offers a clear roadmap to help teams at every stage.

## Assumptions

When utilizing the SCSVS, it's important to consider the following assumptions:

- The SCSVS is not a replacement for standard secure development practices such as **secure coding** or following a **Secure Software Development Life Cycle (SSDLC)**. It should complement these practices by addressing specific security needs for **EVM-based smart contracts** and decentralized applications.

- The SCSVS is not intended to replace comprehensive **threat modeling** or **security reviews**. It serves as a specialized guide to help identify and mitigate vulnerabilities unique to smart contracts. Employing the SCSVS should enhance, not replace, traditional security risk assessments and penetration tests.

While the SCSVS offers a solid framework for improving the security of smart contracts, it cannot ensure complete security on its own. It should be considered a foundational security standard, with additional protective measures added as necessary to address specific vulnerabilities and evolving threats in decentralized environments.
