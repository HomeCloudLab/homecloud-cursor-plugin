# Privacy

This Cursor plugin is configuration only (manifest + Remote MCP URL). It does **not** ship binaries and does **not** store API secrets in the repository.

## Data the plugin touches

1. **OAuth / Console JWT** — Cursor completes HomeCloud Authorization Code + PKCE against `console.<apex>`. The resulting Bearer token is held by Cursor and sent to `https://mcp.<apex>/mcp/`.
2. **MCP tool calls** — HomeCloud runs tools in your signed-in account under existing IAM (`tasks.*`, storage/MQ reads, etc.). The plugin does not add a second policy engine.
3. **Optional `HC_ACCESS_TOKEN`** — Power users may set a Console JWT via CLI (`homecloud mcp env --persist`) instead of OAuth. Treat it like a password; never commit it.

## What we do not do

- Sell plugin usage data
- Train models on your account contents via this plugin package
- Collect secrets into the Git repository

Homepage: https://console.holab.abrdns.com  
Support: open an issue in this repository.
