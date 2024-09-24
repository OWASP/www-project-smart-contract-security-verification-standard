# S6. Cryptographic Practices

## Control Objective
Establish secure cryptographic practices for managing keys, verifying signatures, and generating random numbers to protect the integrity and authenticity of transactions and data within smart contracts.

---

## S6.1 Key Management

### Control Objective
Ensure secure handling and storage of private keys and implement robust signature verification processes to prevent unauthorized access and actions.

### S6.1.A Secure Handling and Storage of Private Keys

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S6.1.A1      | Verify that the ecrecover() function handles malformed inputs correctly and does not return invalid data. |    | ✓  | ✓  |     |
| S6.1.A2      | Ensure that signature verification mechanisms are robust against signature malleability and replay attacks, particularly by using nonces or hashed messages rather than relying solely on the signature itself. |    | ✓  | ✓  |     |
| S6.1.A3      | Verify that SignatureChecker.isValidSignatureNow handles edge cases properly and does not revert unexpectedly, considering the ABI decoding issues introduced in Solidity 0.8. |    | ✓  | ✓  |     |
| S6.1.A4      | Ensure that all signatures are checked thoroughly to prevent unauthorized transactions or actions due to weak or improperly managed signature validation. |    | ✓  | ✓  |     |
| S6.1.A5      | Validate that signature protection mechanisms are up-to-date and resistant to signature malleability attacks by avoiding outdated libraries and practices. |    | ✓  | ✓  |     |

### S6.1.B Multi-Signature Wallets

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S6.1.B1      | Verify that multi-signature wallets require a predefined number of signatures before executing any transaction. |    | ✓  | ✓  |     |
| S6.1.B2      | Ensure that the multi-signature wallet logic is resistant to replay attacks. |    | ✓  | ✓  |     |
| S6.1.B3      | Verify that the process of adding or removing signatories from the multi-signature wallet is secure and controlled. |    | ✓  | ✓  |     |

---

## S6.2 Signature Verification

### Control Objective
Implement cryptographic techniques that ensure the secure verification of signatures and compliance with standards to maintain the integrity of authenticated transactions.

### S6.2.A Cryptographic Techniques for Authentication

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S6.2.A1      | Ensure that cryptographic algorithms used for signature verification are secure and follow best practices. |    | ✓  | ✓  |     |

### S6.2.B Standard Compliance (e.g., EIP-712)

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S6.2.B1      | Verify that ECDSA signature handling functions, such as ECDSA.recover and ECDSA.tryRecover, properly manage signature formats to prevent signature malleability, especially when handling both traditional 65-byte and EIP-2098 compact signatures. |    | ✓  | ✓  |     |

---

## S6.3 Secure Random Number Generation

### Control Objective
Implement best practices for secure random number generation to ensure unpredictability and resistance against manipulation.

### S6.3.A Best Practices for Randomness

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S6.3.A1      | Ensure that random number generation follows best practices and uses secure sources of entropy. |    | ✓  | ✓  |     |
| S6.3.A2      | Verify that any random number generation is resistant to manipulation and prediction. |    | ✓  | ✓  |     |
