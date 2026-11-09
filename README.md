# HomeCloud Cursor plugin

One-click Remote MCP for the [Cursor Marketplace](https://cursor.com/marketplace).

## What you get

- **URL:** `https://mcp.holab.abrdns.com/mcp/`
- **Auth:** OAuth Authorization Code + PKCE (`CLIENT_ID=homecloud-mcp-public`) or Console JWT via `HC_ACCESS_TOKEN`
- **Tools:** Tasks (full surface), Object Storage list tools, Message Queue reads, plus platform/containers tools your IAM allows

## Install (Marketplace)

1. Cursor → **Customize → Plugins / Marketplace** → **HomeCloud** → Add
2. Complete **Connect** (browser sign-in on HomeCloud Console)
3. Tools appear under MCP — no Python, no local `mcp.json`, no PATH

## Local install (before / without Marketplace)

1. Clone this repo (or use the folder in the HomeCloud monorepo).
2. Cursor → Settings → MCP → add from folder, or merge `mcp.json` into your user MCP config.
3. Prefer OAuth Connect when Cursor prompts; or run `homecloud login` then `homecloud mcp env --persist` (CLI ≥ 0.2.57) and **fully restart Cursor**.
4. Agents without interactive login: `homecloud mcp token` (user-bound Access Key → JWT).

## Publish / review notes

- Manifest: `.cursor-plugin/plugin.json`
- MCP: `mcp.json` (remote Streamable HTTP)
- Logo: `assets/logo.svg`
- License: MIT (`LICENSE`)
- Privacy: `PRIVACY.md`

Submit / re-index: [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish)

## Related

- Console: https://console.holab.abrdns.com
- Docs: HomeCloud CLI → MCP
