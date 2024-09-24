# S1. Architecture, Design, and Threat Modeling

## S1.1 Secure Design Patterns

### Control Objective
Ensure that smart contracts are designed with modularity, upgradability, and separation of concerns to enable secure operations, upgrades, and maintenance. Contracts should be designed to minimize security risks related to complex upgrades, privilege transfers, and mismanagement of dependencies.
### Security Verification Requirements
### S1.1.A Modularity and Upgradability

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.1.A1      | Verify that the contract is divided into modular components or contracts.    |    | ✓  | ✓  |     |
| S1.1.A2      | Ensure that upgrade mechanisms are designed to allow secure and controlled updates. |    | ✓  | ✓  |     |
| S1.1.A3      | Check that module boundaries are clearly defined and that dependencies are managed. |    | ✓  | ✓  |     |
| S1.1.A4      | Ensure that changes to storage variable order or types between contract versions are managed to avoid storage collisions and data corruption. |    | ✓  | ✓  |     |
| S1.1.A5      | Verify that critical privilege transfers are conducted in a two-step process to ensure secure and reliable privilege changes. |    |    | ✓  |     |
| S1.1.A6      | Verify that the data location of parameters and return variables is correctly handled when overriding internal and public functions to avoid generating invalid code during virtual function calls. |    |    | ✓  |     |

### S1.1.B Separation of Concerns

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.1.B1      | Verify that different functionalities are separated into distinct contracts or modules. |    | ✓  | ✓  |     |
| S1.1.B2      | Ensure that each module has a single responsibility and minimal dependencies on other modules. |    | ✓  | ✓  |     |
| S1.1.B3      | Check for any cross-module dependencies that could lead to security risks.   |    | ✓  | ✓  |     |
| S1.1.B4      | Ensure that the protocol maintains consistent and reliable operation during the transfer of privileges, with considerations for various edge cases. |    |    | ✓  |     |
| S1.1.B5      | Verify that proxy contracts use the `onlyInitializing` modifier instead of `initializer` to ensure proper initialization. |    |    | ✓  |     |
| S1.1.B6      | Verify that storage layouts between contract versions are consistent to prevent data corruption and unpredictable behavior. |    |    | ✓  |     |
| S1.1.B7      | Ensure that immutable variables are consistent across implementations during proxy upgrades. |    |    | ✓  |     |
| S1.1.B8      | Verify that implementations of the same logic across different parts of the contract are consistent to avoid introducing errors or vulnerabilities. |    |    | ✓  |     |
| S1.1.B9      | Ensure that ETH and WETH are handled separately with appropriate checks to avoid errors due to incorrect assumptions about exclusivity. |    |    | ✓  |     |
| S1.1.B10     | Verify that contracts with constructors are not used in a proxy setup, and initializer logic is used instead. |    |    | ✓  |     |

## S1.2 Proxy Patterns

### Control Objective
Ensure that proxy patterns and upgrade mechanisms are implemented securely and managed properly, to mitigate risks during contract upgrades, deprecations, and transitions between contract versions.
### Security Verification Requirements
### S1.2.A Upgrade Mechanisms

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.2.A1      | Verify that an upgrade mechanism (e.g., proxy pattern) is implemented for the contract. |    | ✓  | ✓  |     |
| S1.2.A2      | Ensure that the upgrade process includes safeguards against unauthorized upgrades. |    | ✓  | ✓  |     |
| S1.2.A3      | Check that the upgrade mechanism is documented and reviewed for security.    |    | ✓  | ✓  |     |
| S1.2.A4      | Verify that immutable variables are consistent across implementations during proxy upgrades to prevent misuse. |    |    | ✓  |     |
| S1.2.A5      | Verify that `selfdestruct` and `delegatecall` in implementation contracts do not introduce vulnerabilities or unexpected behaviors in a proxy setup. |    |    | ✓  |     |
| S1.2.A6      | Verify that UUPSUpgradeable contracts are protected against vulnerabilities that may affect uninitialized implementation contracts, ensuring secure upgrade mechanisms. |    |    | ✓  |     |

### S1.2.B Managing Deprecation

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.2.B1      | Verify that deprecated contract versions are correctly marked and handled.   |    |    | ✓  |     |
| S1.2.B2      | Ensure that access to deprecated versions is restricted or disabled.         |    |    | ✓  |     |
| S1.2.B3      | Check that migration paths from deprecated versions to new versions are secure. |    |    | ✓  |     |

### S1.2.C Transparent vs. Opaque Proxies

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.2.C1      | Verify whether a transparent or opaque proxy pattern is used and its suitability for the contract. |    | ✓  | ✓  |     |
| S1.2.C2      | Ensure that the proxy pattern is correctly implemented and does not introduce vulnerabilities. |    | ✓  | ✓  |     |
| S1.2.C3      | Check that the proxy pattern’s choice is documented and justified.           |    | ✓  | ✓  |     |
| S1.2.C4      | Ensure that uninitialized contracts cannot be taken over by attackers and that initialization functions are secured with the correct modifiers. |    |    | ✓  |     |
| S1.2.C5      | Verify that `TransparentUpgradeableProxy` and similar proxy patterns handle selector clashes and non-decodable calldata correctly to maintain transparency. |    |    | ✓  |     |

## S1.3 Threat Modeling

### Control Objective
Identify, assess, and mitigate security threats for smart contract systems by implementing a thorough threat modeling process, ensuring that risks are minimized and protections are in place for critical contract features.
### Security Verification Requirements
### S1.3.A Identifying Threats

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.3.A1      | Verify that potential threats are identified and documented.                 | ✓  | ✓  | ✓  |     |
| S1.3.A2      | Ensure that the threat identification process includes input from security experts. |    | ✓  | ✓  |     |
| S1.3.A3      | Check that threats are categorized based on their impact and likelihood.     |    | ✓  | ✓  |     |
| S1.3.A4      | Implement protections against front-running in governor proposal creation to prevent attackers from blocking proposals or gaining undue advantages. |    |    | ✓  |     |

### S1.3.B Assessing Risks

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.3.B1      | Verify that risk assessments are performed for identified threats.           |    | ✓  | ✓  |     |
| S1.3.B2      | Ensure that risks are prioritized based on their potential impact and likelihood. |    | ✓  | ✓  |     |
| S1.3.B3      | Check that risk assessment results are documented and reviewed.              |    | ✓  | ✓  |     |

### S1.3.C Implementing Mitigations

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S1.3.C1      | Verify that mitigations are implemented for high-priority risks.             |    | ✓  | ✓  |     |
| S1.3.C2      | Ensure that mitigation strategies are documented and tested.                 |    | ✓  | ✓  |     |
| S1.3.C3      | Check that the effectiveness of implemented mitigations is reviewed and validated. |    | ✓  | ✓  |     |
