# S2. Policies, Procedures, and Code Management

## Control Objective
Ensure that development policies and procedures are in place to promote secure coding practices, thorough code reviews, and comprehensive testing. The aim is to prevent vulnerabilities and enhance the maintainability and clarity of smart contract code.

---

## S2.1 Development Policies

### Control Objective
Establish and enforce secure coding standards and review processes to minimize vulnerabilities and ensure best practices are followed throughout the development lifecycle.

### S2.1.A Secure Coding Standards

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S2.1.A1      | Ensure that developers do not use outdated compiler versions and adhere to the latest compiler recommendations. |    | ✓  | ✓  |     |
| S2.1.A2      | Verify that deprecated functions are not used in the code.                 |    | ✓  | ✓  |     |

### S2.1.B Code Review Processes

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S2.1.B1      | Verify that all smart contract code changes are reviewed by at least two independent developers with expertise in smart contract security before merging to the main branch. |    | ✓  | ✓  |     |
| S2.1.B2      | Ensure that code reviews of smart contracts involve automated static analysis tools specifically designed for smart contracts, and that all flagged issues are addressed or documented prior to merging. |    | ✓  | ✓  |     |
| S2.1.B3      | Check that the code review process for smart contracts includes a thorough analysis for vulnerabilities such as reentrancy attacks, integer overflows, and improper access control. |    | ✓  | ✓  |     |
| S2.1.B4      | Verify that code reviews include adherence to smart contract development standards, such as the use of safe math libraries and secure design patterns. |    | ✓  | ✓  |     |
| S2.1.B5      | Ensure that code reviews incorporate a checklist of common smart contract vulnerabilities, and that each item on the list is addressed before code is approved. |    | ✓  | ✓  |     |

---

## S2.2 Code Clarity

### Control Objective
Promote code clarity and maintainability through thorough documentation, logical structure, and adherence to consistent coding standards, enabling easier understanding and modification by developers.

### S2.2.A Readability and Documentation

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S2.2.A1      | Ensure that all smart contract functions and critical code blocks are documented with clear comments that explain their purpose and logic. |    | ✓  | ✓  |     |
| S2.2.A2      | Verify that the structure of the smart contract is logical and organized to facilitate understanding and modification by other developers. |    | ✓  | ✓  |     |
| S2.2.A3      | Check that the smart contract documentation includes a high-level overview of its functionality, usage instructions, and any dependencies on other contracts or systems. |    | ✓  | ✓  |     |
| S2.2.A4      | Ensure that smart contract code follows consistent naming conventions for variables, functions, and contract names to improve readability and maintainability. |    | ✓  | ✓  |     |

### S2.2.B Code Linting and Formatting Tools

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S2.2.B1      | Ensure that a code linting tool specific to smart contracts is integrated into the development workflow to enforce coding standards and style guidelines. |    | ✓  | ✓  |     |
| S2.2.B2      | Verify that all smart contract code passes linting checks without errors or warnings before being committed to the repository. |    | ✓  | ✓  |     |
| S2.2.B3      | Check that code formatting tools are applied to maintain consistent indentation, spacing, and line breaks in smart contract code. |    | ✓  | ✓  |     |
| S2.2.B4      | Ensure that the linting and formatting configurations are reviewed and updated regularly to reflect new best practices and emerging issues in smart contract development. |    | ✓  | ✓  |     |
| S2.2.B5      | Verify that the linting and formatting tools are compatible with the development environment and do not introduce unintended changes to the smart contract code. |    | ✓  | ✓  |     |

---

## S2.3 Test Coverage

### Control Objective
Ensure comprehensive test coverage for smart contracts, encompassing unit tests, integration tests, and security-specific tests, to identify vulnerabilities and maintain code quality throughout development.

### S2.3.A Unit Tests, Integration Tests, Automated Testing

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S2.3.A1      | Verify that all critical functions in the smart contract have comprehensive unit tests that cover both typical and edge cases. |    | ✓  | ✓  |     |
| S2.3.A2      | Ensure that integration tests are implemented to validate the interactions between the smart contract and other contracts or external systems. |    | ✓  | ✓  |     |
| S2.3.A3      | Check that automated tests are set up to run on each code commit to detect regressions and maintain continuous quality of the smart contract. |    | ✓  | ✓  |     |
| S2.3.A4      | Verify that test coverage tools are used to monitor and achieve a high percentage of coverage for the smart contract code. |    | ✓  | ✓  |     |
| S2.3.A5      | Ensure that the testing framework supports mocking and simulating external dependencies to effectively isolate and test specific functionalities of the smart contract. |    | ✓  | ✓  |     |

### S2.3.B Security-Specific Tests

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S2.3.B1      | Verify that the test suite for the smart contract includes security-specific tests designed to identify vulnerabilities such as reentrancy, integer overflows, and improper access controls. |    | ✓  | ✓  |     |
| S2.3.B2      | Ensure that the security tests validate proper implementation of access controls and permissions within the smart contract. |    | ✓  | ✓  |     |
| S2.3.B3      | Check that fuzz testing is conducted to uncover unexpected behaviors and potential security issues under various input scenarios. |    | ✓  | ✓  |     |
| S2.3.B4      | Verify that the smart contract's response to invalid inputs and edge cases is thoroughly tested to ensure robust security measures are in place. |    | ✓  | ✓  |     |
