# S8. Denial of Service (DoS)

## Control Objective
Establish practices and mechanisms to prevent Denial of Service (DoS) attacks that can disrupt contract functionality and availability.

---

## S8.1 Gas Limits

### Control Objective
Ensure that contract design and function implementations are efficient in gas usage to mitigate risks associated with out-of-gas errors and related vulnerabilities.

### S8.1.A Efficient Loop and Function Design

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S8.1.A1      | Ensure that contracts are protected against insufficient gas griefing attacks by carefully managing gas consumption in critical functions. |    | ✓  | ✓  |     |
| S8.1.A2      | Ensure that systems like the RocketDepositPool contract handle failures in functions like burn() gracefully. |    | ✓  | ✓  |     |
| S8.1.A3      | Verify that gas usage in functions and loops is efficient to avoid out-of-gas errors. |    | ✓  | ✓  |     |
| S8.1.A4      | Implement mechanisms to prevent denial of service attacks due to block gas limits, ensuring that transactions or operations do not exceed the gas limit constraints. |    | ✓  | ✓  |     |

### S8.1.B Fallback Mechanisms

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S8.1.B1      | Ensure that try/catch blocks are provided with adequate gas to avoid failures and unexpected behavior in case of errors. |    | ✓  | ✓  |     |

---

## S8.2 Resilience Against Resource Exhaustion

### Control Objective
Implement strategies to protect contracts from resource exhaustion attacks that can lead to DoS scenarios.

### S8.2.A Rate Limiting

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S8.2.A1      | Avoid using blocking mechanisms that could lead to a Denial-of-Service (DoS) attack. |    | ✓  | ✓  |     |
| S8.2.A2      | Protect against potential DoS in functions like supportsERC165InterfaceUnchecked() by handling excessive data queries efficiently. |    | ✓  | ✓  |     |
| S8.2.A3      | Ensure that assertions do not lead to denial of service or unexpected contract reverts, especially in scenarios where conditions are not met. |    | ✓  | ✓  |     |
| S8.2.A4      | Verify that return values from external function calls are checked to prevent issues related to unchecked return values, which could lead to unexpected behavior. |    | ✓  | ✓  |     |
| S8.2.A5      | Ensure that contract functions are protected against denial of service due to unexpected reverts by handling all possible error conditions appropriately. |    | ✓  | ✓  |     |
| S8.2.A6      | Ensure that functions such as supportsERC165InterfaceUnchecked() in ERC165Checker.sol handle large data queries efficiently to avoid excessive resource consumption. |    | ✓  | ✓  |     |
