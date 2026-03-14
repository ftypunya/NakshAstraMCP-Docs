# 🚀 NakshAstraMCP Setup Guide

> **Quick Start**: Get your local context engine running in under 5 minutes.

---

## 💻 System Requirements

### 1. Install via uv (Recommended)
NakshAstraMCP is distributed as a **Secure Binary Wheel** for maximum privacy and performance.

**📥 [Download v3.2.0 Secure Wheel (Windows)](https://github.com/vijaytank/NakshAstraMCP-Docs/releases/download/3.0.0/nakshastramcp-3.2.0-cp313-cp313-win_amd64.whl)**

We recommend using [uv](https://astral.sh/uv) for installation:

```powershell
# Install uv
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# Install NakshAstraMCP
uv tool install nakshastramcp-3.2.0-cp313-cp313-win_amd64.whl --force
```

### 2. Prerequisite Check
Run the built-in `doctor` command to verify your environment is correctly configured:
```powershell
nakshastramcp doctor
```

---

## ⚙️ Initial Configuration

Once installed, you need to register the codebases you want NakshAstraMCP to index.

### Registering a Workspace
Navigate to your project root and run:
```powershell
nakshastramcp start --workspace .
```
The server will create a local index in your user data directory without modifying your source code.

---

<p align="center">
  <a href="README.md">🏠 Home</a> | 
  <a href="USER_GUIDE.md">📖 User Guide</a> | 
  <a href="TROUBLESHOOTING.md">🛠 Troubleshooting</a>
</p>

---

## 🛡 Security Note
NakshAstraMCP is designed with a "Local First" philosophy. It does not require administrative privileges to index your local files, and it does not connect to any external servers during normal operation.
