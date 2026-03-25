Platforms utilizing the Model Context Protocol (MCP) and Crossmint allow AI agents to act as co-pilots with dual-key smart wallets, requiring strict human-defined spending parameters to ensure safety on Web3 rails.

You need to draft a JSON configuration policy and a corresponding validation function that enforces strict on-chain spending guardrails for an AI agent operating a USDC stablecoin wallet. 

**Constraints:**
- The policy must restrict the agent to a maximum daily spending limit of 50 USDC.
- Transactions formulated by the LLM MUST be validated against a strict whitelist of approved counterparty addresses.
- The validation function must return a specific error code preventing the hardware/TEE signer approval if the agent's intent exceeds the predefined bounds.