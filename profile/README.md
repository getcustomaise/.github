<div align="center">

<img src="https://raw.githubusercontent.com/getcustomaise/.github/main/profile/customaise-logo.svg" alt="Customaise" width="80" />

# Customaise

### The web wasn't built for you. Fix that.

[![Chrome Web Store](https://img.shields.io/badge/Chrome_Web_Store-Install-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)](https://chromewebstore.google.com/detail/customaise/anmpijcpaobaabcdncjjmnhdeibipmko)
[![npm](https://img.shields.io/npm/v/@customaise/mcp?style=for-the-badge&logo=npm&logoColor=white&label=MCP%20Server)](https://www.npmjs.com/package/@customaise/mcp)
[![Website](https://img.shields.io/badge/customaise.com-Visit-000?style=for-the-badge&logo=safari&logoColor=white)](https://customaise.com)

</div>

## The problem

Every day you fight the same broken websites. Cluttered UIs, missing features, repetitive tasks that should take one click but take twelve. You copy-paste workarounds, juggle browser tabs, and accept that "this is just how it works."

It does not have to be.

## What Customaise does

Customaise is a Chrome extension that lets you change how any website looks, behaves, and talks to your AI agents. Describe what you want in plain language, point at the element, or just speak. An autonomous agent plans the change, writes the code, tests it, and installs it. The change runs automatically every time you visit that page.

No coding. No developer tools. No tickets to file. You see a problem, you describe it, it gets fixed.

## Two shapes of one format

Both run on the same metadata-block model, install the same way, and stay portable by design. Export anywhere, anytime.

- **UserScripts** reshape how a page looks and behaves. Hide the chrome, add an export button, force dark mode, automate the seventh click. The format has run on the web for twenty years; the new piece is the in-browser AI that writes and revises scripts for you.
- **AgentScripts** expose the page as a set of tools any connected AI agent can call. Your IDE agent, your in-browser chat, or an autonomous runner can list and invoke those tools through your already-signed-in browser session, with a consent gate on anything sensitive.

Same file, different surface. Pick the one that fits the problem.

## From spotting to sharing

The full arc of working with Customaise, one page at a time:

1. **You spot it.** A friction point on a page you use every day.
2. **You describe it.** One sentence. Point at the element, type in plain language, or use voice in 21 languages.
3. **You see it work.** The AI writes the script, tests it on the live page, and installs it.
4. **You improve it.** Stack more fixes. The script grows with you.
5. **You go deeper.** Connect your IDE through the MCP server. Read, write, and debug from the same chat you ship code in.
6. **Your agent joins in.** AgentScripts turn the page into tools your agent can call on your behalf.
7. **You control it.** Allow, prompt, or deny per tool. Approve sensitive calls from your phone if you're not at your desk.
8. **You share it.** Publish once to your account, auto-updates for every subscriber.

## For developers: MCP server

If you already use an AI coding agent, connect it directly to Customaise. Read, write, and test scripts from your IDE without switching to the browser. When your AgentScripts expose tools via WebMCP, your agent can call them from the same chat.

```json
{
  "mcpServers": {
    "customaise": {
      "command": "npx",
      "args": ["-y", "@customaise/mcp"]
    }
  }
}
```

**18 tools, 5 resources.** Script lifecycle, tab control, browser context, visual DOM targeting, screenshots with element highlighting, WebMCP tool calls with HITL consent. Works with Cursor, Claude Code, Codex, Windsurf, Kiro, Antigravity, and any MCP-compatible editor. Power User plan required.

[MCP docs and source](https://github.com/getcustomaise/customaise-mcp) · [Package on npm](https://www.npmjs.com/package/@customaise/mcp)

## Safe by design

Scripts only touch the visual layer. They can change how a page looks and behaves, but cannot reach backends, databases, or internal APIs. `@grant` declares which browser APIs a script is allowed to use; no declaration, no access. Every edit creates a restore point; undo anything, anytime. Conversations stay encrypted on your device, and your prompts are never used to train models.

## Pricing

- **Free.** 200K monthly in-browser AI tokens, full editor, full script lifecycle, Flash and Flash-Lite models.
- **Power User.** £9 per month or £59 per year. 5M monthly in-browser tokens, MCP server, BYOK (bring your own Gemini key, unlimited in-browser AI), cross-device sync, cloud publishing, Gemini Pro, AgentScript publishing, remote HITL approvals.
- **Token Packs.** £9 for 10M tokens, valid for 12 months. No subscription required.

[See full pricing](https://customaise.com/pricing)

## Links

- [Website](https://customaise.com)
- [Chrome Web Store](https://chromewebstore.google.com/detail/customaise/anmpijcpaobaabcdncjjmnhdeibipmko)
- [Learn UserScripts](https://customaise.com/learn/userscripts)
- [Learn AgentScripts](https://customaise.com/learn/agentscripts)
- [Report a bug](https://github.com/getcustomaise/feedback/issues/new?template=bug_report.md)
- [Request a feature](https://github.com/getcustomaise/feedback/issues/new?template=feature_request.md)
- [Changelog](https://github.com/getcustomaise/feedback/blob/main/CHANGELOG.md)
- [Discussions](https://github.com/getcustomaise/feedback/discussions)
