# 📖 NakshAstraMCP User Guide

> **Master your workflow**: Deep analysis, multi-client connectivity, and visualization.

---

> **Vision**: Empower AI agents with high-fidelity local code context at zero infrastructure cost.

---

## 📋 Prerequisites
- **OS**: Windows 10+ (tested on v11), macOS 12+, or Linux (glibc 2.31+).
- **Hardware**: See the [Hardware Tiers](#-hardware-tiers) section for recommended specifications.

---

## 🚀 Getting Started

### 1. Installation
Ensure [uv](https://astral.sh/uv) is installed, then install the universal wheel:
```powershell
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
uv tool install nakshastramcp-3.5.0-cp313-cp313-win_amd64.whl --force
```

### 2. Configuration for AI Clients

#### Claude Desktop
Add the following to your `claude_desktop_config.json`:
```json
{
  "mcpServers": {
    "nakshastramcp": {
      "command": "nakshastramcp",
      "args": ["start"]
    }
  }
}
```

#### Cursor IDE
1. Open Settings -> Models -> MCP.
2. Add New MCP Server.
3. Name: `NakshAstra`.
4. Command: `nakshastramcp`.
5. Arguments: `start`, `--transport`, `stdio`.

#### Antigravity (mcp_config.json)
Add the following to your `mcp_config.json`:
```json
{
  "mcpServers": {
    "nakshastramcp": {
      "command": "nakshastramcp",
      "args": [
        "start",
        "--transport",
        "stdio"
      ],
      "type": "stdio",
      "disabled": false
    }
  }
}
```

---

## 🌉 Multi-Client Connectivity (Dual Transport Bridge)

NakshAstraMCP introduces a **Dual Transport Bridge**, allowing one host instance to serve multiple clients simultaneously.

### Use Case
You are working in **Antigravity** (Host) while also using **VS Code** (Follower) for specific extensions. Both can connect to the same NakshAstraMCP instance.

### Configuration for Follower Applications
When the host is active, other tools can connect to the bridge:
- **Type**: `streamable-http`
- **URL**: `http://127.0.0.1:2102/mcp`

---

## 💻 Hardware Tiers

NakshAstraMCP automatically adapts its engine capabilities based on your available hardware:

| Tier | Specs | Capabilities |
|------|-------|-------------|
| **Minimal** | 2 cores / 4 GB RAM | Core search engine, aggressive memory management |
| **Recommended** | 4 cores / 8 GB RAM | + Semantic reranking + High-performance indexing |
| **Optimal** | 8+ cores / 16 GB RAM | Full graph analysis + Deep reranking |
| **Massive Repo** | 8+ cores / 16 GB+ RAM | Optimized for repositories with 50k+ files |

**Performance SLA**: p95 query latency under 500ms on a 10,000-file repository.

---

## 🛠️ Important Commands

| Action | Command |
| --- | --- |
| **Start & Register** | `nakshastramcp start --workspace <path>` |
| **Visual Dashboard** | `nakshastramcp ui` |
| **Health Check** | `nakshastramcp doctor` |
| **Cleanup (GC)** | `nakshastramcp gc` |
| **Check Status** | `nakshastramcp status` |
| **Check Version** | `nakshastramcp --version` |

---

## 🔄 Background vs. CLI Management

NakshAstraMCP is designed to be a **"Set it and Forget it"** tool:

1. **Background Management (Daily Use)**:
   When configured in an IDE like **Antigravity**, **Cursor**, or **VS Code**, the server is managed automatically. The IDE spawns the process when it starts and terminates it when it closes. You do not need to manage the server manually.

2. **CLI Management (Advanced Use)**:
   For debugging, health checks, or manual workspace registration, use the commands listed above. The CLI is optional and provided for advanced users.

---

## 🚫 `.mcpignore` Configuration

Control which files and directories are excluded from indexing by placing a `.mcpignore` file in your workspace root. The syntax is identical to `.gitignore`:

```
# Exclude build artifacts
dist/
build/
node_modules/

# Exclude large data files
*.csv
*.parquet
*.sqlite

# Exclude specific directories
vendor/
__pycache__/
.git/
```

> **Tip**: Changes to `.mcpignore` take effect immediately — the real-time watcher picks them up automatically.

---

## 🛡 Security & Privacy
- **Local-Only**: Your code never leaves your machine.
- **Secret Detection**: Automatically prevents indexing of API keys and sensitive strings.
- **Access Control**: The server is locked to the workspace roots you've explicitly registered.
- **Zero Telemetry**: No data collection. Fully local execution.

---

<p align="center">
  <a href="README.md">🏠 Home</a> | 
  <a href="SETUP.md">🚀 Setup Guide</a> | 
  <a href="TROUBLESHOOTING.md">🛠 Troubleshooting</a>
</p>
