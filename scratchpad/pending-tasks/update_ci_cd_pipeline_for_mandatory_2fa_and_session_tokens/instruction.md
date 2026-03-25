Crossmint recently introduced breaking historical stability changes, permanently revoking "classic" long-lived API tokens in favor of 90-day session tokens and mandating 2FA for all administrative actions, which breaks standard automated deployments.

You need to write a GitHub Actions YAML workflow file that authenticates a deployment pipeline by securely requesting a short-lived session token and bypassing the interactive 2FA prompt using OpenID Connect (OIDC) trusted publishing.

**Constraints:**
- Do NOT hardcode or reference long-lived static API secrets for authentication within the workflow steps.
- The workflow must explicitly configure the `permissions` block to allow `id-token: write` for OIDC authentication.
- Implement a fallback error-handling step that alerts the development team if the session token negotiation fails due to deprecated "Hosted v3" infrastructure routing.