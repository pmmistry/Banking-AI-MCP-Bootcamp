<div align="center">

# 🚀 AI-Powered API & MCP Bootcamp
### *Build an Intergalactic Banking API with Agent Mode + MCP*

[![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)](https://www.postman.com/)
[![Claude](https://img.shields.io/badge/Claude_Sonnet-6B46C1?style=for-the-badge&logo=anthropic&logoColor=white)](https://www.anthropic.com/)
[![MCP](https://img.shields.io/badge/MCP-Model_Context_Protocol-0D9276?style=for-the-badge)](https://github.com/postmanlabs/postman-mcp-server)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

**⏱️ 60 Minutes &nbsp;|&nbsp; 🧪 Hands-On &nbsp;|&nbsp; 🤖 No LLM Exp. Required**

[**🌐 Open Bootcamp App**](https://ai-powered-bootcamp-production.up.railway.app/) &nbsp;|&nbsp; [**📮 Postman Workspace**](https://postman.com/devrel/ai-powered-api-mcp-bootcamp) &nbsp;|&nbsp; [**📚 Banking API Repo**](https://github.com/Postman-Devrel/Banking-API-Demo)

<img src="https://voyager.postman.com/logo/postman-logo-orange.svg" alt="Postman Logo" width="200"/>

</div>

---

## 🌌 Mission Briefing

Welcome to the **AI-Powered API & MCP Bootcamp** — a 60-minute hands-on workshop by [Postman](https://www.postman.com/) where you'll build and test an end-to-end **Intergalactic Banking API**, mastering:

- ⚡ AI-accelerated API design & testing with **Postman Agent Mode**
- 🔄 Bridging **code-first and collection-first** workflows using AI
- 🔌 Building **MCP-enabled services** for modern LLM tooling
- 🔁 Applying repeatable Postman techniques for **AI-first API modernization**

---

## ✅ Prerequisites

Before you begin your mission, make sure you have the following:

### 1. Create a Free Postman Account

> **Head to [postman.com](https://www.postman.com/) and sign up for a free account.**

A Postman account gives you access to Agent Mode, Collection Runner, API key management, and the MCP server — everything you need for this bootcamp.

### 2. Access the Postman Bootcamp Workspace

> **Open the [AI-Powered API & MCP Bootcamp Workspace](https://postman.com/devrel/ai-powered-api-mcp-bootcamp) on Postman.**

This public workspace contains the forked collections, environments, and resources you'll use throughout the workshop. Fork the collection into your own workspace to get started.

### 3. (Recommended) Install the Postman Desktop Agent

Download the [Postman Desktop App](https://www.postman.com/downloads/) for the best experience, including local API testing without CORS restrictions.

---

## 🎯 What You'll Build

By the end of this bootcamp, you'll have:

| Deliverable | Description |
|---|---|
| 🏦 Banking API Collection | A fully tested Postman collection for an Intergalactic Banking API |
| 🤖 Agent Mode Workflows | AI-driven test generation and API automation pipelines |
| 🔌 MCP Server Integration | A live MCP server connection queryable by Claude and other LLMs |
| 🧩 Claude Code Plugin | (Bonus) Claude Code wired up to Postman via MCP |

---

## 🗺️ Workshop Structure

The bootcamp is broken into **4 core workflows** plus a bonus module, tracked live in the [bootcamp app](https://ai-powered-bootcamp-production.up.railway.app/).

---

### Workflow 1 — API Spec Import

Get the Banking API collection into your Postman workspace.

- Create a blank Postman workspace
- Fork the Banking API collection from the [public bootcamp workspace](https://postman.com/devrel/ai-powered-api-mcp-bootcamp)

---

### Workflow 2 — Agent Mode Configuration

Set up Postman's AI copilot to supercharge your API work.

1. Enable **Agent Mode** with Claude Sonnet 3.5
2. Create a `Banking.local` environment variable file
3. Configure the `baseUrl` collection variable
4. Generate and set your API key as a **sensitive variable**
5. Add post-request scripts for automatic account/transaction ID extraction

> 💡 **Tip:** Agent Mode acts as your AI co-pilot — use it to draft requests, generate scripts, and debug responses in plain English.

---

### Workflow 3 — Testing & Automation

Let Agent Mode write your tests and run your full collection.

1. Use Agent Mode to generate **status code** and **response time** tests
2. Execute the **Collection Runner** and review test results

---

### Workflow 4 — MCP Server Integration

Connect Postman to the Model Context Protocol for LLM-ready APIs.

1. Generate a **Postman API key**
2. Create an MCP request with **HTTP transport**
3. Query your collections through the [Postman MCP Server](https://github.com/postmanlabs/postman-mcp-server)

```bash
# MCP Server Endpoint
https://mcp.postman.com/mcp
```

---

### 🎁 Bonus — Claude Code Integration

Wire up Claude Code CLI to Postman via MCP for a fully AI-native workflow.

1. Register the Postman MCP Server with Claude Code via CLI
2. Verify the MCP connection
3. Add and run tests through the MCP server

```bash
# Register Postman MCP Server with Claude Code
claude mcp add postman-mcp-server \
  --transport http \
  https://mcp.postman.com/mcp
```

> See the full setup guide: [postman-claude-code-plugin](https://github.com/Postman-Devrel/postman-claude-code-plugin)

---

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| [Postman](https://www.postman.com/) | API platform — collections, testing, environments |
| [Postman Agent Mode](https://academy.postman.com/meet-agent-mode) | AI copilot for API design & test generation |
| [Claude Sonnet 3.5](https://www.anthropic.com/) | LLM powering Agent Mode |
| [MCP (Model Context Protocol)](https://github.com/postmanlabs/postman-mcp-server) | Protocol for connecting LLMs to APIs |
| [Claude Code](https://github.com/Postman-Devrel/postman-claude-code-plugin) | CLI tool for AI-assisted development |

---

## 🔗 All Resources

| Resource | Link |
|---|---|
| 🌐 Bootcamp App | [ai-powered-bootcamp-production.up.railway.app](https://ai-powered-bootcamp-production.up.railway.app/) |
| 📮 Postman Bootcamp Workspace | [postman.com/devrel/ai-powered-api-mcp-bootcamp](https://postman.com/devrel/ai-powered-api-mcp-bootcamp) |
| 🏦 Banking API GitHub Repo | [github.com/Postman-Devrel/Banking-API-Demo](https://github.com/Postman-Devrel/Banking-API-Demo) |
| 🤖 Meet Agent Mode (Academy) | [academy.postman.com/meet-agent-mode](https://academy.postman.com/meet-agent-mode) |
| 📚 Agent Mode Prompt Library | [postman.com/templates/agent-mode](https://postman.com/templates/agent-mode/) |
| 🔌 Postman MCP Server | [github.com/postmanlabs/postman-mcp-server](https://github.com/postmanlabs/postman-mcp-server) |
| 🧩 Claude Code Plugin | [github.com/Postman-Devrel/postman-claude-code-plugin](https://github.com/Postman-Devrel/postman-claude-code-plugin) |

---

## 🚦 Mission Progress

Track your progress live in the [Bootcamp App](https://ai-powered-bootcamp-production.up.railway.app/). There are **15 steps** across 4 workflows to complete your mission.

```
Workflow 1 — API Spec Import      ░░ [ 0 / 2  ]
Workflow 2 — Agent Mode Setup     ░░ [ 0 / 5  ]
Workflow 3 — Testing & Automation ░░ [ 0 / 2  ]
Workflow 4 — MCP Integration      ░░ [ 0 / 3  ]
Bonus      — Claude Code          ░░ [ 0 / 3  ]
─────────────────────────────────────────────
Total                             ░░ [ 0 / 15 ]
```

---

## ❓ Need Help?

- **#PostmanBootcamp** — use the hashtag on social media
- [Postman Community Forum](https://community.postman.com/)
- [Postman Documentation](https://learning.postman.com/docs/)

---

<div align="center">

Built with ❤️ by [Postman](https://www.postman.com/) &nbsp;|&nbsp; [Start the Bootcamp →](https://ai-powered-bootcamp-production.up.railway.app/)

</div>
