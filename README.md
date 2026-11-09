# HomeCloud Cursor plugin

One-click Remote MCP for the [Cursor Marketplace](https://cursor.com/marketplace) and community directories ([cursor.directory](https://cursor.directory)).

## What you get

- **URL:** `https://mcp.holab.abrdns.com/mcp/`
- **Auth:** OAuth Authorization Code + PKCE (`CLIENT_ID=homecloud-mcp-public`) or Console JWT via `HC_ACCESS_TOKEN`
- **Tools:** Tasks (full surface), Object Storage list tools, Message Queue reads, plus platform/containers tools your IAM allows

## Install (Marketplace)

1. Cursor → **Customize → Plugins / Marketplace** → **HomeCloud** → Add
2. Complete **Connect** (browser sign-in on HomeCloud Console)
3. Tools appear under MCP — no Python, no local `mcp.json`, no PATH

## Install (deeplink)

Open this in Cursor (adds the Remote MCP server config):

```text
cursor://anysphere.cursor-deeplink/mcp/install?name=homecloud&config=eyJ1cmwiOiJodHRwczovL21jcC5ob2xhYi5hYnJkbnMuY29tL21jcC8iLCJhdXRoIjp7IkNMSUVOVF9JRCI6ImhvbWVjbG91ZC1tY3AtcHVibGljIn19
```

## Local install (before / without Marketplace)

1. Clone this repo (or use the folder in the HomeCloud monorepo).
2. Cursor → Settings → MCP → add from folder, or merge `mcp.json` into your user MCP config.
3. Prefer OAuth Connect when Cursor prompts; or run `homecloud login` then `homecloud mcp env --persist` (CLI ≥ 0.2.57) and **fully restart Cursor**.
4. Agents without interactive login: `homecloud mcp token` (user-bound Access Key → JWT).

## Package layout

| Path | Purpose |
|------|---------|
| `.cursor-plugin/plugin.json` | Cursor Plugin manifest (official Marketplace) |
| `plugin.json` | Agent Plugins open standard (directories / portable) |
| `mcp.json` | Remote Streamable HTTP MCP + OAuth client id |
| `assets/logo.svg` | Brand mark |
| `LICENSE` / `PRIVACY.md` | MIT + privacy |

## Publish / review notes

### Official Cursor Marketplace (MCP-MKT-04)

Submit / re-index: [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish)  
Requires publisher sign-in + Cursor manual review.

### Community directories (MCP-MKT-05)

1. Confirm this repo is **public**: https://github.com/HomeCloudLab/homecloud-cursor-plugin
2. Open [cursor.directory/plugins/new](https://cursor.directory/plugins/new?type=mcp_server) (GitHub/Google sign-in)
3. **Auto** → paste repo URL → **Scan repo** → publish when MCP component is detected (`mcp.json`)
4. Wait for the directory security scan (`safe` → live)

Other MCP directories (optional): submit the same public repo URL + Remote URL `https://mcp.holab.abrdns.com/mcp/`.

## Related

- Console: https://console.holab.abrdns.com
- Docs: HomeCloud CLI → MCP
