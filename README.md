# Vianido AI plugin

This repository publishes the Vianido plugin, which connects AI agents to [Vianido](https://vianido.com) through the Vianido MCP server (`https://api.vianido.com/mcp`) and skills that explain how to use it. What the plugin does and what each skill covers: [plugins/vianido/README.md](plugins/vianido/README.md).

Full documentation: [Connect an AI agent](https://developer.vianido.com/guides/connect-an-ai-agent).

## Install

### Claude Code

```
/plugin marketplace add vianido/ai
/plugin install vianido@vianido
```

Then run `/mcp`, pick `vianido` and sign in. Approve edit access to get the write tools.

### Codex and the ChatGPT desktop app

```
codex plugin marketplace add vianido/ai
```

Then install **Vianido** from the Plugins Directory and sign in when asked.

### Other MCP clients

Add a remote MCP server with streamable HTTP transport at `https://api.vianido.com/mcp`. The client discovers the OAuth server from the endpoint's 401 response; a client without a client ID metadata document registers itself, as Gemini CLI does. To use the skills, copy the folders in `plugins/vianido/skills/` into the client's skills folder if it supports [Agent Skills](https://agentskills.io).

## Layout

```
.claude-plugin/marketplace.json     Claude Code marketplace
.agents/plugins/marketplace.json    Codex / ChatGPT marketplace
plugins/vianido/
  .claude-plugin/plugin.json        Claude Code manifest
  .mcp.json                         Claude Code MCP server
  README.md                         Plugin description, used for directory listings
  plugin.json                       Agent Plugins manifest (Codex, ChatGPT)
  mcp.json                          Agent Plugins MCP server
  assets/                           Icon shown in plugin listings
  skills/                           Skills, shared by every client
    vianido-search/                 Finding and citing nonprofits
    vianido-profile/                Updating an organization you manage, metrics included
    vianido-about-page/             Drafting and publishing its About page
    vianido-updates/                Posting and managing its updates
    vianido-writing/                Writing profile text that is specific and true
```

The two MCP files describe the same server: Claude Code reads `.mcp.json` (`type: http`), the Agent Plugins format reads `mcp.json` (`type: streamable-http`). Keep them in step.

## Versioning

Versions follow the Vianido platform's calendar scheme, `YYYY.M.N`: the year, the month without a leading zero, and the release number within that month, starting at `0` (`2026.11.0`, then `2026.11.1`, then `2026.12.0`). Set the same version in both manifests.

## Develop

```
claude plugin validate ./plugins/vianido
claude --plugin-dir ./plugins/vianido
```
