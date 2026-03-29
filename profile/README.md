<div align="center">

<img src="https://raw.githubusercontent.com/getcustomaise/.github/main/profile/customaise-logo.svg" alt="Customaise" width="80" />

# Customaise

### Fix any website. No code. No waiting.

[![Chrome Web Store](https://img.shields.io/badge/Chrome_Web_Store-Install-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)](https://chromewebstore.google.com/detail/customaise/anmpijcpaobaabcdncjjmnhdeibipmko)
[![npm](https://img.shields.io/npm/v/@customaise/mcp?style=for-the-badge&logo=npm&logoColor=white&label=MCP%20Server)](https://www.npmjs.com/package/@customaise/mcp)
[![Website](https://img.shields.io/badge/customaise.com-Visit-000?style=for-the-badge&logo=safari&logoColor=white)](https://customaise.com)

</div>

## The problem

Every day you fight the same broken websites. Cluttered UIs, missing features, repetitive tasks that should take one click but take twelve. You copy-paste workarounds, juggle browser tabs, and accept that "this is just how it works."

It does not have to be.

## What Customaise does

Customaise is a Chrome extension that lets you change how any website looks and behaves. Tell it what you want in plain English (or point at the element, or just speak). An autonomous AI agent plans the fix, writes the code, tests it, and installs it. The change runs automatically every time you visit that page.

No coding. No developer tools. No tickets to file. You see a problem, you describe it, it gets fixed.

## Why this over Tampermonkey or Violentmonkey

Tampermonkey gives you a text box and expects you to write JavaScript. Customaise gives you an AI agent that writes it for you.

- **You describe, AI delivers.** Point at elements, type in plain language, or use voice in 21 languages. The agent does the rest.
- **Full compatibility.** Import your existing .user.js scripts. Tampermonkey metadata, @match rules, GM_* APIs all work.
- **Built-in safety net.** Every edit creates a version. Unlimited undo. Nothing is ever lost.
- **Real code editor.** Monaco (the VS Code engine) with syntax highlighting, validation, and AI-assisted debugging.
- **Privacy by default.** Conversations encrypted on-device. No AI training on your data. Period.

## For developers: MCP integration

If you already use an AI coding agent, connect it directly to Customaise. Create, test, and manage userscripts from your IDE without switching to the browser.

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

13 tools available: script lifecycle, visual DOM targeting, browser context, screenshots with element highlighting, and guided workflows.

Compatible with Cursor, Claude Code, Windsurf, Kiro, Antigravity, and any MCP-compatible editor. Power User plan required.

[View MCP docs and source](https://github.com/getcustomaise/customaise-mcp)

## Links

- [Website](https://customaise.com)
- [Chrome Web Store](https://chromewebstore.google.com/detail/customaise/anmpijcpaobaabcdncjjmnhdeibipmko)
- [Report a bug](https://github.com/getcustomaise/feedback/issues/new?template=bug_report.md)
- [Request a feature](https://github.com/getcustomaise/feedback/issues/new?template=feature_request.md)
- [Changelog](https://github.com/getcustomaise/feedback/blob/main/CHANGELOG.md)
- [Discussions](https://github.com/getcustomaise/feedback/discussions)
