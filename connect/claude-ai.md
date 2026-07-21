# Connect: claude.ai / Claude for Science

The Claude Code marketplace/plugin path doesn't apply on the web — claude.ai and Claude for
Science connect to ViaFoundry as an MCP **custom connector** instead.

## Add the connector

1. In claude.ai (or your Claude for Science workspace), open **Settings → Connectors** and choose
   to add a **custom connector**.
2. Enter your ViaFoundry MCP URL: `https://<your-instance>/mcp` (replace `<your-instance>` with
   your ViaFoundry base URL).
3. Click **Connect**. This opens a browser window to sign in to ViaFoundry (OAuth) and provisions
   the access token for you automatically — there's nothing to copy or paste.

Once connected, ask Claude things like "show my last 5 runs" and it will call the ViaFoundry MCP
tools directly.

## Find your URL in ViaFoundry

Your ViaFoundry account has a **Connect to Claude** page (under your profile) that shows the
exact connector URL for your instance, plus a list of your active Claude connections that you can
revoke individually.

## PAT fallback (no OAuth)

If your ViaFoundry instance predates the OAuth build, the custom-connector OAuth flow won't be
available. In that case, create a Personal Access Token in ViaFoundry (your account → Personal
Access Tokens — it starts with `via_mcp_`) and use it wherever your Claude for Science/claude.ai
connector setup accepts an auth token or header (`X-Foundry-Connect-Token: via_mcp_...`) instead of the
OAuth "Connect" button. Check your workspace admin if custom-connector auth headers aren't exposed
in your claude.ai settings.
