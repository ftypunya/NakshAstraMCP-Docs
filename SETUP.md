## 🚀 Installation Steps

### 1. Install via uv (Recommended)
NakshAstraMCP is distributed as a **Secure Binary Wheel** for maximum privacy and performance. We recommend using [uv](https://astral.sh/uv) for installation:

```powershell
# Install uv
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# Install NakshAstraMCP
uv tool install "path\to\nakshastramcp-3.1.0-cp313-cp313-win_amd64.whl" --force
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

## 🛡 Security Note
NakshAstraMCP is designed with a "Local First" philosophy. It does not require administrative privileges to index your local files, and it does not connect to any external servers during normal operation.
