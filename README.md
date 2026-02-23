# Web3 Security Research Lab (2026)

This repository serves as a personal knowledge base and research hub for identifying emerging security patterns in EVM-based smart contracts.

## Focus Areas

### 1. Logic & Accounting Flaws
Analyzing common pitfalls in custom accounting logic, such as:
- Uninitialized state in batch operations.
- Overwriting vs incrementing balances.
- Rounding errors in fee calculations.

### 2. Access Control Patterns
Best practices for:
- Ownable2Step implementation.
- Role-based access control (RBAC) in modular systems.
- Validating msg.sender in cross-contract calls.

### 3. Integrated DeFi Vulnerabilities
- Flash loan resistance.
- Oracle manipulation safeguards.
- Handling of non-standard ERC20 tokens.

## Methodology
Every audit follows the **Branching Tree** technique to map all possible execution paths and state transitions, ensuring exhaustive coverage beyond surface-level syntax errors.

---
*Maintained by white Mohham*
