# Install the Meta Ads MCP server (steps for AI agents)

This is a hosted (remote) MCP server. There is nothing to download or run. Setup guide for people: https://adkit.so/features/ads-mcp/meta

1. Add an HTTP MCP server named `adkit-meta-ads` with the URL `https://mcp.adkit.so/meta-ads`.
2. The server uses OAuth. When the client opens the sign-in page, the user signs in to AdKit or creates an account (7-day free trial at https://adkit.so).
3. Call `adkit_projects` with `operation: "projects.list"` to pick a project, then `adkit_status` to see the connected ad accounts.
4. If no Meta Ads account is connected, call `meta_ads_accounts_read` with `operation: "accounts.available"`. If the user still needs to sign in to Meta Ads, call `adkit_setup` with `platform: "meta"` and share the `setupUrl`.
5. Every change is saved as a draft. Publish with `adkit_drafts_publish` only after the user approves it.
