# S3. Business Logic and Economic Security

## Control Objective
Ensure that the smart contract's business logic and economic security are resilient against threats related to incentive structures, tokenomics, and logic vulnerabilities. Contracts should prevent abuse, misbehavior, or unexpected behaviors by implementing secure economic models, token handling, and transaction integrity.

---

## S3.1 Economic Models

### Control Objective
Ensure that economic models, including incentive structures and tokenomics, are designed and implemented in a way that secures value and incentivizes proper behavior within the ecosystem. Contracts should handle fluctuating token values and avoid creating opportunities for exploitation.

### S3.1.A Incentive Structures

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S3.1.A1      | Ensure that the withdrawal process implements a pull-based approach rather than a push-based one to track accounting and allow users to pull payments. | ✓  | ✓  | ✓  |     |
| S3.1.A2      | The rate of cbETH to ETH can decrease, impacting users who hold or interact with cbETH. Ensure mechanisms are in place to handle fluctuations in conversion rates. |    | ✓  | ✓  |     |
| S3.1.A3      | Validators on the Ethereum 2.0 Beacon Chain can be penalized or slashed for misbehavior, which can affect the value of rETH. Ensure that these dynamics are considered in value assessments and interactions. |    | ✓  | ✓  |     |
| S3.1.A4      | The conversion rate between ETH and rETH might change over time based on the rewards accrued from staking. Ensure that these fluctuations are properly managed and captured. |    | ✓  | ✓  |     |

---

## S3.2 Tokenomics

### Control Objective
Ensure that tokens used within the smart contract ecosystem are securely implemented, including aspects such as value management, rebasing mechanisms, and reward systems. Contracts should prevent token vulnerabilities like double-spending, incorrect rewards, and improper fee handling.

### S3.2.A Economic Security of Tokens and Their Use Cases

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S3.2.A1      | Ensure that Merkle trees do not contain duplicate proofs, as this can lead to vulnerabilities like double-spending. |    | ✓  | ✓  |     |
| S3.2.A2      | Verify that DeFi protocols account for tokens with negative rebase mechanisms, ensuring that value changes and potential miscalculations are properly handled and mitigated. |    | ✓  | ✓  |     |
| S3.2.A3      | Verify that reward claims are correctly implemented to ensure users receive their correct rewards. |    | ✓  | ✓  |     |
| S3.2.A4      | Verify that tokens do not have vulnerabilities such as incorrect fee application or unexpected behavior due to token transfer issues. |    | ✓  | ✓  |     |
| S3.2.A5      | Verify that all claimable addresses are included in the hashing process for Merkle tree leaves to prevent attackers from claiming funds they should not. |    | ✓  | ✓  |     |

---

## S3.3 Preventing Reentrancy and Logic Flaws

### Control Objective
Ensure the smart contract's transaction flow and logic integrity are protected from reentrancy attacks and logic flaws. Contracts should implement robust control structures and security patterns to prevent reentrancy, handle complex flows, and ensure that state transitions are secure and symmetrical.

### S3.3.A Transaction Flow Security

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S3.3.A1      | Check for edge cases in loop control structures to prevent unexpected behaviors due to break or continue statements. |    | ✓  | ✓  |     |
| S3.3.A2      | Ensure that scenarios where sender and recipient are the same are considered to prevent unintended issues in smart contracts. |    | ✓  | ✓  |     |
| S3.3.A3      | Ensure that the `NonReentrant` modifier is applied before other modifiers in functions to prevent reentrancy attacks. |    | ✓  | ✓  |     |
| S3.3.A4      | Verify that the check-effect-interaction pattern is implemented to prevent reentrancy attacks. |    | ✓  | ✓  |     |
| S3.3.A5      | Ensure that function calls with arbitrary user input and low-level calls are handled securely to avoid introducing risks. |    | ✓  | ✓  |     |

### S3.3.B Function Integrity

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S3.3.B1      | Ensure that functions intended to be unique per parameter set are not callable multiple times to prevent potential issues. |    | ✓  | ✓  |     |
| S3.3.B2      | Verify that state changes in functions, such as withdraw and deposit, are symmetrically handled to avoid undesired behavior due to inconsistencies. |    | ✓  | ✓  |     |
