Headless commerce architectures decouple the frontend from backend payment logic. Crossmint allows for custom, native Web3 checkout flows without relying on standardized iframe modals.

You need to create a Next.js serverless backend API route (`/api/checkout`) that accepts credit card payment details, securely calls the Crossmint fiat-to-crypto API to handle background KYC/AML, and dynamically mints a digital asset.

**Constraints:**
- The asset must be minted to a newly generated embedded wallet, not a pre-existing EOA.
- All Crossmint API keys and granular environmental scopes (e.g., `wallets.fund`, `users.create`) MUST be isolated on the server side and never exposed to the client payload.
- Return a JSON response containing the transaction hash and the newly provisioned embedded wallet address.