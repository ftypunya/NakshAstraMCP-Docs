# NakshAstraMCP — User Guide

> **Vision**: Empower AI agents with high-fidelity local code context at zero infrastructure cost.

---

## 📋 Prerequisites
- **OS**: Windows (tested on v11), macOS, or Linux.
- **Hardware**: Refer to the hardware tiers section for recommended specifications.

---

## 🚀 Getting Started

### 1. Download & Placement
Download the latest standalone executable (`nakshastramcp.exe` or equivalent for your OS). Place it in a dedicated directory and optionally add it to your system's PATH.

### 2. Configuration for AI Clients

#### Claude Desktop
Add the following to your `claude_desktop_config.json`:
```json
{
  "mcpServers": {
    "nakshastramcp": {
      "command": "C:\\path\\to\\nakshastramcp.exe",
      "args": ["start"]
    }
  }
}
```

#### Cursor IDE / Antigravity
1. Open Settings -> Models -> MCP.
2. Add New MCP Server.
3. Name: `NakshAstra`.
4. Command: `C:\path\to\nakshastramcp.exe`.
5. Arguments: `start`, `--transport`, `stdio`.

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

## 🛠️ Important Commands

| Action | Command |
| --- | --- |
| **Start & Register** | `nakshastramcp.exe start --workspace <path>` |
| **Visual Dashboard** | `nakshastramcp.exe ui` |
| **Health Check** | `nakshastramcp.exe doctor` |
| **Cleanup (GC)** | `nakshastramcp.exe gc` |
| **Check Health** | `nakshastramcp.exe status` |
| **Check Version** | `nakshastramcp.exe --version` |

---

## 🛡 Security & Privacy
- **Local-Only**: Your code never leaves your machine.
- **Secret Detection**: Automatically prevents indexing of API keys and sensitive strings.
- **Access Control**: The server is locked to the workspace roots you've explicitly registered.
- **Zero Telemetry**: No data collection. Fully local execution.
