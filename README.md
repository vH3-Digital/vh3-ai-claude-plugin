# VH3 AI plugin for Claude

Ask Claude about your field service operation: jobs, engineers, sites, customers, quotes, invoices and scheduling. The plugin connects Claude to VH3 AI and adds a skill and three commands so Claude uses the tools well.

## What it contains

- **Connector** (`.mcp.json`): one remote MCP server, `https://mcp.vh3.ai/mcp` (HTTP). It is the same URL as the VH3 AI directory connector, so having both installed shows one tool set. Sign-in happens in the browser through VH3 on first use. The plugin holds no keys, headers or tokens.
- **Skill** `field-service`: how to choose the right tool, date and unit rules, quote and invoice reporting rules, scheduling rules and how to present answers.
- **Commands**: `/vh3-ai:morning-brief`, `/vh3-ai:weekly-review`, `/vh3-ai:who-can-take`.

## What it connects to and sends

The plugin connects to one service only: `https://mcp.vh3.ai/mcp`, operated by VH3 Digital. When you ask a question, Claude sends the tool inputs it chose (for example a date range, a job or customer ID, a search term, a postcode) to that server over HTTPS, signed with the access token you granted at sign-in. The server returns data for your own company only. The plugin does not run local code, hooks or background processes, and sends nothing anywhere else. If you tick "Allow actions" at sign-in, Claude can also ask Connie, VH3's assistant, to send email or SMS, send notifications, create Gmail drafts, build presentations and queue Quote Runs; Claude asks before every such call. Without it, every tool is read-only.

## Install

- **Claude Code**: run `/plugin`, add this repository as a marketplace source or install from the directory listing, then enable `vh3-ai`. To try a local checkout: `claude --plugin-dir ./vh3-ai-claude-plugin`.
- **claude.ai or Cowork**: Customize, then Plugins, then upload the plugin as a zip of this repository (zip the repository root, so `.claude-plugin/plugin.json` is at the top level).

Then ask, for example, "how are we doing this week?", or run `/vh3-ai:who-can-take JOB123`.

## Validate

```bash
claude plugin validate --strict .
```

## Maintainer notes

- The icon in `assets/icon.png` is a placeholder. The final icon comes from ticket #838.
- TODO, to confirm before submission: `supportUrl` (https://vh3.ai/support), `privacyPolicyUrl` (https://vh3.ai/privacy), `termsOfServiceUrl` (https://vh3.ai/terms), and the licence (MIT chosen for this plugin; the main VH3 repository is all rights reserved).
- Keep out of this repo: `bin/`, hooks, local MCP servers, `.mcpb` bundles, `.DS_Store`, files over 256 KiB.
