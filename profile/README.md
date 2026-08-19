<div align="center">

<img src="https://raw.githubusercontent.com/getcustomaise/.github/main/profile/customaise-logo.svg" alt="Customaise" width="80" />

# Customaise

### Custom programmable tools for every open tab. For you, or for your AI.

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

## The Browser Agent tests your scripts

Writing a script is the easy half. Knowing it actually works on the live page is the rest, and that is the Browser Agent's job.

When Chat builds or revises a script, it can deploy the Browser Agent to check the result. The agent reloads the page, drives it the way you would (clicking, typing, dragging, keyboard shortcuts), and reports PASS, FAIL, or INCONCLUSIVE against the criteria it was given, with the observations behind the verdict. "Clicking the dark mode toggle switches the background and leaves every label readable" is the shape of question it answers.

Input arrives as real browser input rather than synthetic events, so canvas apps and sites that ignore scripted clicks respond to it the way they respond to you. An action it cannot carry out says so instead of reporting success, which is what makes a FAIL worth acting on.

It runs on Gemini Computer Use, so it needs a Google model to drive it. On a model that cannot, the tool is withheld and the reason is shown.

## On-device AI (Chrome 148+)

Chrome 148+ ships with built-in Gemini Nano via the Prompt API. Pick Nano as the model in Chat for prompts that stay on your device, or declare `@grant CM_promptAI` in a script and call `await CM_promptAI(prompt, opts?)` directly. No API key, no per-call cost, no inference network call. Single-shot prompts, streaming, multi-turn sessions, and image and audio analysis are all supported.

## Bring your own model

The Chat that writes your scripts does not have to run on our inference.

- **Your own hardware.** Point Customaise at llama.cpp, Ollama, LM Studio or vLLM and that model joins the Chat model picker beside the cloud ones. Over localhost, or a Tailscale name when the machine is a rig in another room. Prompts go from the browser straight to your server, so they draw no tokens: the request never reaches us to be counted. Power User.
- **Your own key.** Save a Google AI Studio or OpenRouter key on your Account page and pick any model that key serves. Hold both at once; each model runs on its own provider's key, billed by that provider.
- **On-device.** Gemini Nano, as above. No key, no server, no inference network call at all.

## From spotting to sharing

The full arc of working with Customaise, one page at a time:

1. **You spot it.** A page you want to change.
2. **You describe it.** One sentence, in plain language. Or point at the element. Or use voice.
3. **You see it work.** The first change lands. The AI writes the script, tests it on the live page, and installs it.
4. **You improve it.** Stack more fixes. The script grows with you.
5. **You go deeper.** Bigger ask, same flow. Connect your IDE through the MCP server. Read, write, and debug from the same chat you ship code in.
6. **You give your agent tools.** AgentScripts turn the page into tools your agent can call, in your signed-in browser session.
7. **You control it.** Allow, prompt, or deny per tool. Approve sensitive calls from your phone if you're not at your desk.
8. **You share it.** Publish once, auto-updates for every subscriber.

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

Every capability a script or agent wants is declared up front and enforced by the extension.

- **`@grant` for browser APIs.** A script lists which `GM_*` APIs it needs; no declaration, no access. No `GM_xmlhttpRequest`, no network calls, full stop.
- **`@connect` for network hosts.** Any request a script makes is gated to an explicit allowlist of hosts in the metadata block.
- **SRI on `@require` and `@resource`.** Third-party code pulled in by a script is integrity-checked before it runs.
- **Per-tool consent for AgentScripts.** Each WebMCP tool is `allow`, `prompt`, or `deny`. Prompt-gated tools pause and wait for your explicit OK, per call. "Always allow" and "Always deny" persist per script, per tool.
- **Remote HITL.** Sensitive calls can route to your Account Portal and wait for approval from any signed-in browser, including your phone. Tool arguments are KMS-encrypted at rest.
- **Origin-locked MCP bridge.** The local WebSocket the MCP server uses only accepts connections from known Customaise extension IDs. A random webpage cannot reach it.
- **Restore points on every edit.** Unlimited undo. Nothing is ever lost.
- **On-device chat encryption.** AES-256-GCM with a key only you control. Your prompts are never used to train models.

## Pricing

- **Free.** Full editor, full script lifecycle, monthly in-browser AI included.
- **Power User.** From $9 / £7 / €9 per month (or $72 / £60 / €72 yearly). Unlocks the MCP server, cross-device sync, cloud publishing, AgentScript publishing, a larger in-browser AI allowance, and remote HITL approvals.
- **Token Packs.** $9 / £7 / €9 for 10M tokens, valid for 12 months. No subscription required.

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
