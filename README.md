# AlertChecker MCP Server

Gives any MCP-compatible AI assistant (ChatGPT, Claude, and others) the ability to create AI-monitored web alerts on your behalf. Then you will be told when something happens instead of having to ask — just say **"Alert me when..."**

## What it does

AlertChecker watches the web for you and emails you when a plain-English statement becomes true. Once you connect this MCP server, any supporting AI assistant can create these alerts directly from natural conversation.

**Example prompts:**
- "Alert me when the iPhone 16 Pro is back in stock at apple.com"
- "Let me know whenever it's going to rain in London tomorrow"
- "Alert me when Tesla stock drops below $200"
- "Tell me if there's an earthquake over 4.0 magnitude in California"

## Tools

| Tool | Description |
|---|---|
| `create_alert` | Creates an alert that monitors the web and emails you when a statement becomes true (or false). Accepts a statement, a short title, confidence level, and which outcome to notify on. |

## Icon

A public icon suitable for connector setup is available at [alertchecker.com/app-icon.png](https://alertchecker.com/app-icon.png) — PNG, 256x269px, under 9KB.

## Connecting

**Server URL:** `https://alertchecker.com/api/mcp`

**Transport:** Streamable HTTP

**Authentication:** OAuth 2.0 with PKCE and Dynamic Client Registration (RFC 7591). No manual API key or client credentials needed — your MCP client discovers everything automatically from:
```
https://alertchecker.com/.well-known/oauth-authorization-server
```

On first connection, you'll be redirected to sign in via Google or a magic email link.

### Adding to ChatGPT

1. Go to **Settings → Plugins → Browse plugins**
2. Click the **New Plugin** button (plus icon, top-right)
3. Fill in:
   - **Icon** (optional): upload [alertchecker.com/app-icon.png](https://alertchecker.com/app-icon.png) — otherwise a generic icon is shown
   - **Name**: `AlertChecker`
   - **Description**: `Create AI-monitored web alerts from plain English`
   - **Connection** ("Server URL" option selected): `https://alertchecker.com/api/mcp`
   - **Authentication**: `OAuth`
4. Tick the checkbox confirming you understand the risks
5. Click **Create**, then click **Sign in with AlertChecker** — you'll be redirected to sign in via Google or magic link
6. In a new chat, enable AlertChecker from the "Add files and more" button (plus icon, just to the left of where you type your chat). Then ask: *"Alert me when..."*

### Adding to Claude

1. Go to **Settings → Customize → Connectors → Add → Add custom connector**
2. Fill in:
   - **Name**: `AlertChecker`
   - **Remote MCP server URL**: `https://alertchecker.com/api/mcp`
3. Click **Add**
4. Click **Connect**
5. Sign in
6. Optionally change **Needs approval** to **Always allow** for the **Create alert** tool
7. In a new chat, enable AlertChecker from the **Connectors** submenu under the "Add files, connectors and more" button (plus icon, just to the left of where you type your chat). Then ask: *"Alert me when..."*

### Adding to Perplexity

1. Go to **All settings → Connectors → Add custom connector** (top-right)
2. Click **Change icon** and upload [alertchecker.com/app-icon.png](https://alertchecker.com/app-icon.png)
3. Fill in:
   - **Name**: `AlertChecker`
   - **Description** (optional): `Create AI-monitored web alerts from plain English`
   - **MCP Server URL**: `https://alertchecker.com/api/mcp`
4. Tick the checkbox confirming you understand the risks
5. Sign in when prompted
6. In a new chat, enable AlertChecker from the "Add files or tools" button (plus icon, just to the left of where you type your chat). Then ask: *"Alert me when..."*

## Learn more

- [AlertChecker](https://alertchecker.com) — the main app
- [Model Context Protocol](https://modelcontextprotocol.io) — the open standard this server implements

## Support

Questions or issues: [support@alertchecker.com](mailto:support@alertchecker.com)
