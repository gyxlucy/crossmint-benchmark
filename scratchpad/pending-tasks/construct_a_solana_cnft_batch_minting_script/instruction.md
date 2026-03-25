Minting massive NFT collections on Solana relies on state compression utilizing Concurrent Merkle Trees to reduce costs exponentially compared to EVM chains. 

You need to write a Node.js script utilizing the Crossmint API and `mpl-bubblegum` logic to append a new leaf (NFT data) to an off-chain Merkle tree hosted by an RPC provider, and output the payload required to update the on-chain root hash.

**Constraints:**
- The script must explicitly define the interaction between the off-chain RPC provider (e.g., Quicknode or Alchemy) and the on-chain single root account.
- Do NOT utilize standard SPL token minting; the solution must strictly use the compressed NFT (cNFT) programmatic flow.
- Ensure the script handles API rate limits or potential error retries for high-volume execution.