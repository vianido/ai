# Vianido

Connect your AI assistant to [Vianido](https://vianido.com), the public record of US nonprofits, and ask it about nonprofits in plain words. For example, it can:

- find food banks or youth programs in a city, or nonprofits working on a cause;
- read their profiles and compare them, such as their missions, causes and where they work;
- keep your organization's profile, About page and updates current, if you manage one on Vianido, checking each change with you first.

The plugin adds the Vianido MCP server and skills that teach the assistant to use it well. You sign in to Vianido and approve the connection once. After that the assistant works for you, with your account.

## Install

In Claude Code:

```
/plugin install vianido --marketplace vianido/ai
```

Then run `/mcp`, pick `vianido` and sign in. In Codex or the ChatGPT desktop app, run `codex plugin marketplace add vianido/ai` and install **Vianido** from the Plugins Directory.

## Sign in and approve

When you connect, your browser opens at Vianido. Sign in, and Vianido shows a consent screen naming the app that asks and what it may do:

- **View access** lets the assistant read anything you can see on Vianido: organizations, causes and places, and your own account.
- **Edit access** also lets it change the organizations you manage: the profile, logo, social links, metrics, media, About page and updates. It can never change an organization you don't manage.

To disconnect, open your Vianido account page and remove the app under Connected apps.

## A first conversation

Once connected, try asking:

- "Find food banks in Riverbend and compare their missions."
- "Which organizations do I manage on Vianido?"
- "Update the mission of my organization to the one on its website, but check it with me first."
- "Draft an update about Saturday's volunteer day with these photos."

For a change, the assistant first runs it as a check and tells you whether it would pass. Confirm, and it makes the change, which goes live on Vianido at once. Changes to the About page and new updates are saved as drafts, and the assistant publishes or schedules them only when you ask.

## Skills

- **vianido-search**: finding nonprofits by name, cause or place, and citing them.
- **vianido-profile**: updating an organization you manage, from one field to a first full profile.
- **vianido-about-page**: planning, drafting and publishing its About page.
- **vianido-updates**: drafting, publishing, scheduling and featuring its updates.
- **vianido-writing**: keeping profile text specific, true and in the organization's own voice.

## What the plugin sends and fetches

The plugin's only connection is the Vianido MCP server at `https://api.vianido.com/mcp`, through the tools your assistant calls. It has no hooks, no scripts and no local code: only the server's address and the skills' instructions.

## Links

- Documentation: [Connect an AI agent](https://developer.vianido.com/guides/connect-an-ai-agent)
- Privacy policy: [vianido.com/privacy](https://vianido.com/privacy)
- Terms of service: [vianido.com/terms](https://vianido.com/terms)
- Support: [vianido.com/contact](https://vianido.com/contact)
