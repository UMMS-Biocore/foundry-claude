# Connect: Claude Desktop

Like claude.ai, Claude Desktop connects to ViaFoundry as an MCP connector — not through the
Claude Code marketplace/plugin.

## Option A: add the connector in settings

1. Open Claude Desktop's **Settings → Connectors** and add a **custom connector**.
2. Enter your ViaFoundry MCP URL: `https://<your-instance>/mcp` (replace `<your-instance>` with
   your ViaFoundry base URL).
3. Confirm — Desktop opens a browser window for OAuth sign-in to ViaFoundry and provisions the
   token automatically, same as claude.ai. No key to copy or paste.

## Option B: import a `.mcpb` bundle

If your ViaFoundry administrator has provided a `.mcpb` bundle for your instance, you can install
it instead of typing the URL by hand — open it (or use Desktop's **Settings → Extensions →
Install from file**) and Desktop will configure the connector for you. Not every ViaFoundry
deployment publishes a bundle; if none is available, use Option A.

## PAT fallback (no OAuth)

If your instance doesn't have the OAuth build, create a Personal Access Token in ViaFoundry (your
account → Personal Access Tokens — it starts with `via_mcp_`) and supply it as the connector's
auth token, or as an `X-Foundry-Connect-Token: via_mcp_...` header if your Desktop version exposes
custom headers for connectors, instead of using the OAuth "Connect" step.
