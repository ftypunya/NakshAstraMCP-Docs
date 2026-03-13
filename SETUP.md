# NakshAstraMCP — Setup Guide

This guide provides detailed instructions for installing and setting up NakshAstraMCP on your system using the official standalone binary distribution.

---

## 💻 System Requirements

### Hardware Tiers
| Tier | Specs | Engines Enabled |
|------|-------|-----------------|
| **Minimal** | 2c / 4GB | Basic Search, Low-Memory Guard |
| **Recommended** | 4c / 8GB | Full Semantic Search & Reranking |
| **Optimal** | 8c / 16GB | Full Graph Analysis, Deep Reranking |

### Supported Operating Systems
- **Windows**: v10 or v11 (64-bit)
- **macOS**: v12 (Monterey) or later
- **Linux**: Standard x86_64 distributions

---

## 🚀 Installation Steps

### 1. Download the Binary
Download the latest version of `nakshastramcp.exe` (Windows) or the equivalent executable for your platform.

> [!IMPORTANT]
> This is a **fully compiled standalone distribution**. You do **not** need to install Python, pip, or set up any virtual environments.

> [!TIP]
> Always download the accompanying `.pdb` (Windows) or debug symbols for your platform to assist with advanced troubleshooting if required.

### 2. Verify the Executable (Optional)
On Windows, you can verify the file hash using PowerShell:
```powershell
Get-FileHash .\nakshastramcp.exe
```
Compare the output with the hash provided on the release page.

### 3. Add to System PATH (Recommended)
Adding the executable to your system PATH allows you to run `nakshastramcp` from any terminal window.

**On Windows:**
1. Open the **Start Search**, type in “env”, and choose “Edit the system environment variables”.
2. Click the **Environment Variables** button.
3. Under **User variables**, select **Path** and click **Edit**.
4. Click **New** and paste the folder path where you saved `nakshastramcp.exe`.
5. Click **OK** on all windows.

### 4. Prerequisite Check
Run the built-in `doctor` command to verify your environment is ready:
```powershell
nakshastramcp.exe doctor
```

---

## ⚙️ Initial Configuration

Once installed, you need to register the codebases you want NakshAstraMCP to index.

### Registering a Workspace
Navigate to your project root and run:
```powershell
nakshastramcp.exe start --workspace .
```
The server will create a local index in your user data directory without modifying your source code.

---

## 🛡 Security Note
NakshAstraMCP is designed with a "Local First" philosophy. It does not require administrative privileges to index your local files, and it does not connect to any external servers during normal operation.
