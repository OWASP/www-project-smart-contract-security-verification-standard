# Assessment and Certification

## OWASP's Stance on SCSVS Certifications and Trust Marks

OWASP, as a vendor-neutral not-for-profit organization, does not currently certify any vendors, verifiers, or smart contracts.

All such assurance assertions, trust marks, or certifications are not officially vetted, registered, or certified by OWASP. Therefore, organizations relying on third-party verification or certifications must carefully evaluate the trust placed in any external entity or trust mark claiming **Smart Contract Security Verification Standard (SCSVS)** certification.

This should not discourage organizations from offering security verification or audit services, as long as they do not claim to provide official OWASP certification.

## Guidance for Certifying Organizations

For Smart Contract Security Verification Standard (SCSVS) compliance, an "open book" review is recommended, where assessors are granted access to essential resources such as smart contract developers, project documentation, source code, and authenticated blockchain interfaces (including access to the blockchain explorer, transaction logs, and testing environments). It's essential that assessors gain access to at least one account for each user role, particularly if the contract supports permissioned or role-based access.

It is important to note that the SCSVS only covers the security requirements specific to **EVM-based smart contracts** and does not extend to general application security controls (e.g., web interfaces, databases, or other non-blockchain components). Any additional systems or non-blockchain elements should be verified against appropriate security standards, such as the [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/).

### Certification Reports

Certification reports should clearly define the scope of the verification, specifying which smart contracts, components, or decentralized applications (dApps) were reviewed, and should list any excluded items from the review. The report should summarize the findings, detailing both passed and failed security controls, alongside guidance on how to remediate any failures.

Industry-standard practices for security certification require thorough documentation of the verification process. This should include:

- **Work papers**: Notes and records on each step of the verification process.
- **Screenshots**: Evidence of security control tests, such as transaction hashes or audit results.
- **Scripts**: Used for testing and replication of discovered issues.
- **Blockchain logs**: Detailed records of the verification process including contract interactions, transactions, and gas usage.

Automated tools alone are insufficient to verify SCSVS compliance. All verification reports must provide conclusive, manually validated evidence that demonstrates the thorough and accurate testing of all required controls. In case of disputes, documentation should include adequate evidence to confirm that each control has been appropriately tested and validated.
