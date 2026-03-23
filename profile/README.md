<div align="center">

<img src="https://raw.githubusercontent.com/getcustomaise/.github/main/profile/customaise-logo.svg" alt="Customaise" width="80" />

# Customaise

### AI-Powered Chrome Extension to Fix, Customize, and Automate Any Website

[![Chrome Web Store](https://img.shields.io/badge/Chrome_Web_Store-Install-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)](https://chromewebstore.google.com/detail/customaise/anmpijcpaobaabcdncjjmnhdeibipmko)
[![npm](https://img.shields.io/npm/v/@customaise/mcp?style=for-the-badge&logo=npm&logoColor=white&label=MCP%20Server)](https://www.npmjs.com/package/@customaise/mcp)
[![Website](https://img.shields.io/badge/customaise.com-Visit-000?style=for-the-badge&logo=safari&logoColor=white)](https://customaise.com)

---

</div>

### ✨ What is Customaise?

Customaise is a Chrome extension that lets you create, manage, and run **userscripts** on any website — powered by AI. Whether you want to clean up a cluttered UI, add missing features, automate repetitive tasks, or pull data from pages — Customaise makes it possible without any web development experience.

- 🤖 **AI Chat** — Describe what you want in plain English; the AI writes the script for you
- 📝 **Built-in Editor** — Full Monaco editor with syntax highlighting, validation, and symbol navigation
- 🔒 **Safe by Default** — Every script passes through AST validation and a sanitization pipeline
- 📦 **Import & Export** — Standard `.user.js` format, compatible with Tampermonkey and Violentmonkey scripts
- ⏱ **Version History** — Wayback Machine for your scripts with full commit-level history
- 🌐 **Works Everywhere** — Run scripts on any website via flexible URL match patterns

### 🤖 MCP Integration for AI Coding Agents

Connect your IDE's AI agent directly to Customaise for a seamless scripting workflow:

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

12 tools available — script management, browser context, DOM snapshots, console logs, screenshots, and more.

Works with **Cursor** · **Claude Code** · **Windsurf** · **Antigravity** · any MCP-compatible IDE.

→ [View MCP Server docs](https://github.com/getcustomaise/customaise-mcp)

### 📬 Community

- 🐛 [Report a Bug](https://github.com/getcustomaise/feedback/issues/new?template=bug_report.md)
- 💡 [Request a Feature](https://github.com/getcustomaise/feedback/issues/new?template=feature_request.md)
- 📋 [Changelog](https://github.com/getcustomaise/feedback/blob/main/CHANGELOG.md)
- 💬 [Discussions](https://github.com/getcustomaise/feedback/discussions)
