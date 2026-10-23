# Awesome-Mobile-Devops-Deployment

## Top Model Context Protocol (MCP) Tools Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Tool Discovery, OAuth-Managed Connectivity & Standardized Server Implementations*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for the **Model Context Protocol (MCP)**. MCP is an open standard that lets AI assistants securely access tools and data sources — filesystems, databases, APIs, and SaaS apps — through a unified interface. These tools provide the servers, registries, and platforms that make MCP practical at scale.

**Examples** include the official reference servers, Composio, Smithery, Superface, and the curated community lists (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, standardized tool interfaces, and transparent server implementations — ideal for developers building agent integrations who need portability across clients rather than vendor-specific plugins.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Composio** — **The managed MCP connectivity layer for 1000+ apps.** Handles OAuth, permissions, and intelligent tool routing, with a **remote sandbox for bulk data processing** so large tool responses don't flood the context window [citation:5]. Exposes **7 meta-tools** instead of thousands of individual app tools: search, connect via managed OAuth, execute, and process results in a remote workbench. Compatible with Claude Code, Codex, Cursor, and any MCP client [citation:5]. **Best for teams wanting managed OAuth and cross-app workflows** without building individual connectors.

- **Smithery** — **The MCP server registry and hosting platform.** Provides a searchable API for discovering MCP servers by name, description, tags, or qualified name [citation:6]. Supports filtering by remote/local, verified status, and deployment status. **Best for developers wanting to discover and install MCP servers** without browsing scattered GitHub repos.

- **Superface** — **The MCP server that exposes selected Superface tools via a managed API key.** Configure which tools you want in the Superface dashboard, copy your API key, and add the server to Claude Desktop or any MCP client via npx or Docker [citation:8]. **Best for teams already using Superface's API integration platform** wanting MCP access to their configured tools.

## Open-Source GitHub Projects

- **[Official Reference Servers (modelcontextprotocol/servers)](https://github.com/modelcontextprotocol/servers)** — **The canonical MCP server implementations maintained by the protocol authors.** Apache 2.0 licensed. **v2.0.0 refactored all servers to support the modern era spec while answering legacy clients** [citation:4]. **Current reference servers**: **Everything** (test server with prompts, resources, tools), **Fetch** (web content fetching for LLM usage), **Filesystem** (secure file operations with configurable access controls), **Git** (read, search, manipulate Git repos), **Memory** (knowledge graph-based persistent memory), **Sequential Thinking** (dynamic reflective problem-solving), and **Time** (timezone conversion) [citation:11]. **Best for any MCP implementation** — these are the reference patterns every other server follows.

- **[punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers)** — **The most comprehensive curated list of MCP servers.** The de facto community directory, cited in academic papers and referenced by the official MCP documentation [citation:9][citation:12]. **Organized by category with emoji tags** indicating language (🐍 Python, 📇 TypeScript, #️⃣ C#), deployment (☁️ cloud, 🏠 local), and platform (🍎 macOS, 🪟 Windows, 🐧 Linux) [citation:1]. **Includes servers for**: Java semantic analysis, Godot GDScript analysis, C#/.NET Roslyn analysis, JMeter/k6/Locust performance testing, Docker management, Xcode integration, App Store release automation, OpenAPI discovery, Excel automation, WCAG accessibility testing, RAG flight recording, and self-evolving LLM tool generation [citation:1]. **Best for discovering community servers** across every conceivable integration.

- **[OpenTools](https://arxiv.org/html/2604.00137v2)** — **The community-driven framework for reliable, standardized AI agent tools.** Academic paper (CC BY 4.0). **Review-oriented lifecycle**: each tool has a natural-language description, typed JSON schema, output contract, and tool card recording dependencies, provenance, limitations, risk evidence, and evaluation history [citation:15]. **Layered non-executing inspection** before any functional test: AST analyzer identifies syntax errors, credential access, filesystem writes, network capabilities, and embedded secrets; integrates Gitleaks, detect-secrets, Bandit, and Semgrep [citation:15]. **Gated evaluation** — the hosted interface inspects but does not execute newly uploaded tools; maintainers run functional tests locally for selected tools that satisfy risk policy [citation:15]. **MCP integration** supports discovery, inspection, evaluation, and invocation of explicitly allowlisted tools [citation:15]. **Best for teams wanting vetted, reliable tool contributions** rather than an unmoderated registry.

- **[OpenTool SDK](https://pypi.org/project/opentool-sdk/)** — **Python SDK for the OpenTool MCP server.** MIT licensed. **Sync and async clients** for managing tools, auth, and API keys programmatically [citation:7]. **Tool execution via MCP**: `client.tools.execute("github.create_issue", {...})` [citation:7]. **OAuth connection management**: `client.auth.get_connect_url("github")` returns a URL the user visits to authorize [citation:7]. **API key management**: list, create, and revoke keys with raw key returned once [citation:7]. **Best for Python developers** wanting programmatic control over MCP tool connections.

### Additional Strong Open-Source Options

- **bgizdov/awesome-mcp-servers** — Automatically generated MCP server list with regular updates [citation:2].
- **ever-works/awesome-mcp-servers** — Another curated list with categorized detail files .
- **mcp-openapi** — Discover OpenAPI specs and generate callable MCP tools with Bearer, API key, and Basic auth support [citation:1].
- **mcp-broker** — Local MCP broker exposing one client entry that routes to many upstream servers with profile gates and mutating-tool allowlists [citation:1].

**Frameworks for building custom systems**: Combine **Official Reference Servers** for canonical implementation patterns, **Composio** for managed OAuth across 1000+ apps with remote sandbox processing, **Smithery** for server discovery and registry search, **OpenTools** for vetted community contributions with risk evaluation, and **punkpeye/awesome-mcp-servers** for breadth of community integrations — to build an MCP toolchain tailored to your client (Claude, Cursor, Codex), connectivity requirements (OAuth vs local), and governance needs.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- MCP servers differ significantly in deployment model (local stdio vs remote HTTP), authentication requirements, and risk profile. **The official reference servers are the safest starting point** — they demonstrate correct patterns and are maintained by the protocol authors [citation:11]. **Community server quality varies** — the punkpeye list is comprehensive but unmoderated [citation:1], while OpenTools provides a gated review process with AST inspection and maintainer approval [citation:15]. **OAuth-managed platforms like Composio** simplify connectivity but route tool calls through their infrastructure [citation:5]. **Always review what filesystem access, network capabilities, and credential handling an MCP server requests** before connecting it to your agent.
- Self-hosted open-source solutions require proper Node.js or Python environment setup depending on the server, and awareness that local stdio servers run with the permissions of the process that launched them.

---

**Made for AI engineers building agent integrations on the open MCP standard.**
Let's make MCP tooling more open, standardized, and security-reviewed.
