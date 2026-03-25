Developers integrating the `@crossmint/wallets-sdk` frequently encounter an issue where the `setJwt()` function fails to rehydrate the JSON Web Token (JWT) across page navigations, causing unexpected logouts. 

You need to create a React context provider wrapper that securely persists the Crossmint session token in `sessionStorage` and automatically rehydrates the authentication state using `setJwt()` upon component initialization in a Next.js environment. 

**Constraints:**
- Do NOT use `localStorage` for storing the JWT due to XSS vulnerability risks; strictly use `sessionStorage` or secure HTTP-only cookies.
- Ensure the rehydration logic only executes on the client-side to prevent Next.js hydration mismatch errors.
- The wrapper must gracefully handle token expiration scenarios by prompting a re-authentication flow.