# NakshAstraMCP — Troubleshooting Guide

This guide helps resolve common issues encountered while setting up or using NakshAstraMCP.

---

## 🔍 Diagnostic Tool: `doctor`

The first step for any issue is to run the built-in diagnostic tool. This verifies your environment, permissions, and dependencies.

```powershell
nakshastramcp doctor
```

Review the output for any checks marked as **FAILED** or **WARNING**.

---

## 🛠 Common Issues

### 1. Protocol Error: `invalid character '_' looking for beginning of value`
If your IDE (VS Code, Cursor, etc.) shows this error, it's typically because the IDE is trying to read the protocol via `stdio`, but the server is printing an informative banner or log message to the same stream.

**Fix**: Ensure your IDE configuration includes the `--transport stdio` flag. This correctly isolates the protocol stream from informative messages.
```json
"args": ["start", "--transport", "stdio"]
```

### 2. Dual Transport Bridge Port Conflicts
The background HTTP bridge defaults to port `2102`. If this port is in use, the bridge will fail to start, though the host `stdio` session (IDE) will remain functional.

**Fix**: You can specify a custom port for the bridge:
```powershell
nakshastramcp start --port 3000
```
Then, update your follower applications to connect to `http://127.0.0.1:3000/mcp`.

### 3. Server Not Responding / Indexing Issues
If the server appears slow or search results are outdated:
- **Check Status**: Run `nakshastramcp status` to see if indexing is in progress or if there are high memory alerts.
- **Run GC**: If memory usage is high, run `nakshastramcp gc` to trigger an immediate garbage collection.
- **Identify Workspace**: Ensure the workspace is registered correctly. If needed, re-register using `nakshastramcp start --workspace <path>`.

---

## 📁 Log Files

If you need to investigate further, NakshAstraMCP maintains logs in your platform's standard user data directory.

- **Windows**: `%LOCALAPPDATA%\nakshastramcp\logs`
- **Linux**: `~/.local/share/nakshastramcp/logs`
- **macOS**: `~/Library/Application Support/nakshastramcp/logs`

When reporting a bug, please include the relevant logs from the last session. **Note**: Source code snippets are never logged; only indexing counts and performance metrics are tracked.
