# S11. Component-Specific Security

## Control Objective
Establish security practices and standards for various blockchain components to mitigate specific vulnerabilities associated with tokens, NFTs, vaults, and liquidity pools.

---

## S11.1 Tokens (ERC20, ERC721, ERC1155)

### Control Objective
Ensure secure implementation and management of token standards to prevent vulnerabilities.

### S11.1.A Secure Implementation and Management

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S11.1.A1     | Verify that the totalSupply value is consistent during token minting operations, ensuring that callbacks do not result in incorrect values. |    | ✓  | ✓  |     |
| S11.1.A2     | Some tokens have multiple addresses associated with them, which can introduce vulnerabilities. Ensure all token addresses are managed and verified securely to avoid related risks. |    | ✓  | ✓  |     |
| S11.1.A3     | Verify that tokens handle zero amount transfers properly to prevent issues in integrations and operations. |    | ✓  | ✓  |     |
| S11.1.A4     | Verify that tokens handle zero amount transfers properly to prevent issues in integrations and operations. |    | ✓  | ✓  |     |
| S11.1.A5     | Some tokens revert on the transfer of a zero amount, which can cause issues in certain integrations and operations. Ensure compatibility with such tokens to avoid integration problems. |    | ✓  | ✓  |     |
| S11.1.A6     | Not all ERC20 tokens comply with the EIP20 standard; some may not return a boolean flag or revert on failure. Verify compliance with the ERC20 standard to avoid compatibility issues. |    | ✓  | ✓  |     |

---

## S11.2 NFT Security

### Control Objective
Implement best practices for non-fungible tokens to safeguard against vulnerabilities.

### S11.2.A Best Practices for Non-Fungible Tokens

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S11.2.A1     | Implement standards and best practices for NFT creation, management, and transfer to prevent common vulnerabilities. |    | ✓  | ✓  |     |
| S11.2.A2     | Ensure proper metadata integrity and prevent unauthorized minting or transfers. |    | ✓  | ✓  |     |
| S11.2.A3     | Safeguard against potential exploits related to royalty payments or token burns. |    | ✓  | ✓  |     |

---

## S11.3 Vaults

### Control Objective
Ensure secure asset storage and management within vault systems.

### S11.3.A Secure Asset Storage and Management

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S11.3.A1     | Address potential overhead issues associated with withdrawing stETH or wstETH, including queue times and withdrawal limits, to ensure smooth operations. |    | ✓  | ✓  |     |
| S11.3.A2     | Handle conversions between stETH and wstETH carefully to avoid potential issues due to the rebasing nature of stETH. |    | ✓  | ✓  |     |

---

## S11.4 Liquid Staking

### Control Objective
Ensure secure staking mechanisms to protect users' assets.

### S11.4.A Secure Staking Mechanisms

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S11.4.A1     | Verify that mechanisms for detaching sfrxETH from frxETH are robust to prevent discrepancies and ensure accurate reward transfers, particularly when controlled by centralized entities. |    | ✓  | ✓  |     |
| S11.4.A2     | Monitor potential future changes in the sfrxETH/ETH rate and ensure users are adequately forewarned to mitigate risks associated with rate fluctuations. |    | ✓  | ✓  |     |

---

## S11.5 Liquidity Pools (AMMs)

### Control Objective
Establish security measures in automated market makers.

### S11.5.A Security in Automated Market Makers

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S11.5.A1     | [WIP/Will be removed]                                                     |    |    |    |     |

---

## S11.6 Uniswap V4 Hook

### Control Objective
Ensure secure integration and customization of Uniswap components.

### S11.6.A Secure Integration and Customization

| Ref          | Requirement                                                                 | L1 | L2 | L3 | SWE |
| ------------ | --------------------------------------------------------------------------- | -- | -- | -- | --- |
| S11.6.A1     | Verify the correct usage of Uniswap’s TickMath and FullMath libraries to ensure proper handling of unchecked arithmetic operations, adhering to version-specific Solidity considerations. |    | ✓  | ✓  |     |
