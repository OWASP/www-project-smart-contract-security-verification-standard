# S5. Secure Interactions and Communications

## Control Objective
Establish secure interaction protocols for smart contracts to ensure safe communication between contracts, external oracles, and cross-chain integrations. This includes managing contract interactions, securing oracle integrations, handling cross-chain interactions, and ensuring the security of bridges.

---

## S5.1 Contract Interactions

### Control Objective
Ensure that all interactions between contracts are secure, minimizing risks associated with external calls, maintaining a minimal trusted surface, and handling errors appropriately.

### S5.1.A Secure Message Passing

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.1.A1      | Ensure that calls to inherited functions from LzApp use recommended approaches (e.g., _lzSend) to avoid vulnerabilities associated with direct calls to lzEndpoint.send. |    | ✓  | ✓  |     |
| S5.1.A2      | Ensure that when interacting with external contracts, the msg.sender remains consistent to avoid security issues related to unexpected changes in sender context. |    | ✓  | ✓  |     |
| S5.1.A3      | Manage untrusted external contract calls to prevent unexpected results such as multiple withdrawals or out-of-order events. |    | ✓  | ✓  |     |
| S5.1.A4      | Missing verification of interacting pools can introduce risks. Ensure that all pools are properly verified before interaction to prevent potential security issues. |    | ✓  | ✓  |     |
| S5.1.A5      | Verify that the low-level .delegatecall() is properly managed, acknowledging that it converts the return value to a Boolean without providing the execution outcome. |    | ✓  | ✓  |     |

### S5.1.B Minimal Trusted Surface

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.1.B1      | Verify that the smart contract minimizes its trusted surface by only interacting with other contracts and systems through well-defined and limited interfaces. |    | ✓  | ✓  |     |
| S5.1.B2      | Ensure that the smart contract includes checks to validate the trustworthiness and authenticity of interacting parties before executing sensitive operations. |    | ✓  | ✓  |     |
| S5.1.B3      | Check that the smart contract's interactions are designed to avoid dependencies on external data or contracts that could compromise security. |    | ✓  | ✓  |     |
| S5.1.B4      | Verify that the contract handles failures or unexpected behaviors from external interactions gracefully to avoid cascading failures. |    | ✓  | ✓  |     |
| S5.1.B5      | Ensure that interactions with other contracts are monitored and audited to detect and address any unusual or unauthorized activities. |    | ✓  | ✓  |     |

---

## S5.2 Oracle Integrations

### Control Objective
Ensure that oracle integrations provide secure, reliable, and tamper-proof data feeds while maintaining data integrity and handling failures appropriately.

### S5.2.A Secure Data Feeds

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.2.A1      | Verify that the smart contract uses oracles that provide secure and tamper-proof data feeds, including checks for data integrity and authenticity. |    | ✓  | ✓  |     |
| S5.2.A2      | Ensure that the smart contract validates the data received from oracles to prevent malicious or incorrect data from affecting contract operations. |    | ✓  | ✓  |     |
| S5.2.A3      | Check that the smart contract includes fallback mechanisms in case of oracle failure or unreliable data. |    | ✓  | ✓  |     |
| S5.2.A4      | Verify that the integration with oracles follows best practices for data security, including encryption and secure communication channels. |    | ✓  | ✓  |     |
| S5.2.A5      | Ensure that the smart contract's oracle integration is designed to handle any potential discrepancies or conflicts in data from multiple sources. |    | ✓  | ✓  |     |

### S5.2.B Decentralized Oracles

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.2.B1      | Verify that the smart contract uses decentralized oracles to enhance data reliability and prevent single points of failure or manipulation. |    | ✓  | ✓  |     |
| S5.2.B2      | Ensure that the smart contract includes mechanisms to validate the consensus or majority opinion of decentralized oracles before taking actions based on their data. |    | ✓  | ✓  |     |
| S5.2.B3      | Check that the smart contract accounts for potential latency or delays in data from decentralized oracles to maintain operational reliability. |    | ✓  | ✓  |     |
| S5.2.B4      | Verify that the smart contract includes checks to prevent manipulation or collusion among decentralized oracles. |    | ✓  | ✓  |     |
| S5.2.B5      | Ensure that the decentralized oracle integration adheres to standards for security and reliability in multi-oracle environments. |    | ✓  | ✓  |     |

---

## S5.3 Cross-Chain Interactions

### Control Objective
Ensure secure handling of external calls and atomic swaps during cross-chain interactions to maintain operational reliability and prevent fraud.

### S5.3.A Handling External Calls Securely

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.3.A1      | Ensure that parameters for Chainlink VRF (Verifiable Random Function) are thoroughly validated to prevent the fulfillRandomWord function from returning incorrect values instead of reverting. |    | ✓  | ✓  |     |
| S5.3.A2      | Implement robust security checks for cross-chain messaging to ensure correct permissions and intended functionality. |    | ✓  | ✓  |     |
| S5.3.A3      | Verify that contracts created using the CREATE opcode handle block reorganizations securely to prevent unexpected eliminations. |    | ✓  | ✓  |     |
| S5.3.A4      | Ensure robust cross-chain messaging security checks to prevent replay attacks where signatures valid on one chain might be exploited on another. |    | ✓  | ✓  |     |

### S5.3.B Atomic Swaps

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.3.B1      | Verify that the smart contract supports atomic swaps with robust mechanisms to ensure that swaps are completed successfully or not executed at all. |    | ✓  | ✓  |     |
| S5.3.B2      | Ensure that the smart contract includes checks to validate the atomic swap conditions and prevent partial or fraudulent swaps. |    | ✓  | ✓  |     |
| S5.3.B3      | Check that the smart contract handles potential failures or disputes in atomic swaps securely and fairly. |    | ✓  | ✓  |     |
| S5.3.B4      | Verify that the atomic swap functionality is tested thoroughly to cover various scenarios and edge cases. |    | ✓  | ✓  |     |

---

## S5.4 Bridges

### Control Objective
Ensure the security of cross-chain transactions by implementing robust validation and verification mechanisms to prevent fraud and maintain data integrity.

### S5.4.A Cross-Chain Transaction Security

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S5.4.A1      | Verify that the smart contract for cross-chain transactions includes robust mechanisms for verifying and validating transactions across different chains. |    | ✓  | ✓  |     |
| S5.4.A2      | Ensure that the smart contract prevents double-spending and replay attacks in cross-chain transactions by implementing appropriate security checks. |    | ✓  | ✓  |     |
| S5.4.A3      | Check that the cross-chain transaction contract handles communication and data integrity securely between different blockchain networks. |    | ✓  | ✓  |     |
| S5.4.A4      | Verify that the smart contract includes fallback and recovery mechanisms for handling failures or inconsistencies in cross-chain transactions. |    | ✓  | ✓  |     |
