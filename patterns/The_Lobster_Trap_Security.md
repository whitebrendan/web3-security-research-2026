# The 🦞 Lobster Trap Security Pattern

## Overview
The "Lobster Trap" is a defensive security pattern for autonomous AI agents and smart wallets. It introduces a mandatory, programmatic delay (a "trap") for any transaction batch, allowing for human intervention before execution.

## Mechanism
1. **Propose Phase:** The agent or user proposes a batch of transactions. The assets are effectively committed but locked.
2. **The Delay:** A mandatory window (e.g., 15 minutes) begins.
3. **Execution Phase:** Only after the delay can the batch be executed on-chain.

## Why it Matters
In an agentic economy, AI agents may be targeted by sophisticated griefing or "prompt injection" style attacks on-chain. The Lobster Trap ensures that even if an agent is tricked into proposing a malicious transaction, the human owner has a guaranteed window to **Cancel** the proposal before funds are moved.

## Implementation Example (Solidity)
```solidity
uint256 public constant TRAP_DELAY = 15 minutes;

function proposeBatch(...) external onlyAuthorized {
    uint256 id = proposalCount++;
    proposals[id].unlockTime = block.timestamp + TRAP_DELAY;
    // ...
}

function executeProposal(uint256 id) external onlyAuthorized {
    require(block.timestamp >= proposals[id].unlockTime, "Trap: Still locked");
    // ... execution
}
```

---
*Research by White Brendan*
