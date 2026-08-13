# 🚀 RDP-v5.0 Azure Workstation

> Turn a GitHub Actions Windows runner into a fully controllable remote workstation with RDP, SSH, Tailscale, Cloudflare Tunnel, WSL, Docker, Guacamole, AI-powered Telegram control, and more.

![Windows](https://img.shields.io/badge/Windows-Server-blue)
![RDP](https://img.shields.io/badge/RDP-Enabled-green)
![SSH](https://img.shields.io/badge/OpenSSH-Enabled-success)
![Tailscale](https://img.shields.io/badge/Tailscale-Connected-purple)
![Telegram](https://img.shields.io/badge/Telegram-Controlled-2CA5E0)
![Cloudflare](https://img.shields.io/badge/Cloudflare-Tunnel-orange)

---

## ✨ What is this?

This workflow transforms a standard GitHub Actions Windows runner into a temporary cloud workstation that can be accessed and managed remotely.

Once started, the workflow automatically:

🔹 Enables Remote Desktop (RDP)  
🔹 Installs and configures OpenSSH  
🔹 Connects the machine to your Tailscale network  
🔹 Creates secure remote access channels  
🔹 Deploys a Telegram-controlled management bot  
🔹 Installs workstation utilities and development tools  
🔹 Supports Cloudflare Tunnel exposure  
🔹 Provides AI assistance through Groq

The result is a fully interactive Windows environment accessible from anywhere.

---

# 🖥️ Remote Access

## 🔐 Remote Desktop (RDP)

The workflow automatically configures Windows Remote Desktop and generates a password for the `runneradmin` account.

Features:

- Automatic RDP activation
- Firewall rule configuration
- Password generation
- Remote GUI access
- Tailscale-compatible connection

Perfect for:

- Software testing
- Development
- Remote administration
- Browser automation

---

## 🖥️ OpenSSH Server

SSH access is enabled automatically.

This allows:

- Terminal access
- Script execution
- File management
- Automation workflows

The SSH service starts automatically and remains available during the workflow runtime.

---

## 🌐 Tailscale Integration

Instead of exposing ports directly to the internet, the runner joins your private Tailscale network.

Benefits:

✅ End-to-end encryption  
✅ Private networking  
✅ Stable connectivity  
✅ No router configuration required  
✅ Direct RDP and SSH access

The runner receives its own Tailscale IP address and can even advertise itself as an Exit Node if desired.

---

# 🤖 Telegram Control Center

The workstation can be managed entirely from Telegram.

After startup, the bot becomes your remote control panel.

Supported capabilities include:

### 💻 Execute Commands

Run:

- CMD commands
- PowerShell commands
- Linux commands through WSL

Examples:

```text
/cmd ipconfig

/ps Get-Process

/wsl uname -a
```

---

### 📸 Capture Screenshots

Need to see what's happening?

```text
/screenshot
```

The bot captures the active desktop and sends it directly back to Telegram.

---

### 📊 View System Status

```text
/status
```

Displays information about:

- CPU usage
- Memory usage
- Network state
- Running services
- Workstation status

---

### 📂 File Transfer

The bot supports:

⬆️ Uploading files to the workstation

⬇️ Downloading files from the workstation

Useful for:

- Source code
- Logs
- Installers
- Build artifacts

---

# 🧠 AI Assistant

Integrated Groq AI support provides a built-in assistant directly inside Telegram.

Instead of memorizing commands, you can simply ask:

```text
How do I install Docker?
```

or

```text
Show me how to start Apache.
```

The assistant responds directly within Telegram and can help with workstation-related tasks and troubleshooting.

---

# ☁️ Cloudflare Tunnel

Need public access to a local service?

The workflow includes Cloudflared support.

Example:

```text
/expose 8080
```

Returns a temporary public URL such as:

```text
https://example.trycloudflare.com
```

Perfect for:

- Web applications
- APIs
- Development servers
- Dashboards
- Temporary demos

No port forwarding required.

---

# 🐧 Linux Environment (WSL)

The workstation can deploy Ubuntu through Windows Subsystem for Linux (WSL).

This provides:

- Native Linux tools
- Package management
- Docker support
- Bash environment
- Network utilities

You effectively get both Windows and Linux inside the same GitHub Actions runner.

---

# 🐳 Docker Support

Docker can be installed automatically during setup.

This enables:

- Containerized applications
- Development environments
- Self-hosted services
- Testing environments

Run Linux workloads directly from the temporary workstation.

---

# 🌍 Browser-Based Desktop (Guacamole)

For users who don't want to use a traditional RDP client, the workflow can deploy Apache Guacamole.

Benefits:

✅ Browser access  
✅ No RDP software required  
✅ Cross-platform compatibility  
✅ Easy sharing and testing

Access your desktop directly through a web browser.

---

# ⚡ Additional Utilities

The workstation also includes several useful tools:

### 📈 Speedtest CLI

Measure:

- Download speed
- Upload speed
- Latency

---

### 🔎 Nmap

Perform:

- Host discovery
- Port scanning
- Service enumeration

Useful for diagnostics and testing environments.

---

### 🌐 Cloudflared

Create secure public tunnels for local services.

---

### 🔧 Networking Utilities

Additional networking tools are installed to assist with troubleshooting and connectivity management.

---

# 🔒 Security

Several measures are implemented:

- Telegram user validation
- Private Tailscale networking
- Temporary GitHub runner environment
- Secure secret storage through GitHub Actions
- Optional Cloudflare exposure only when requested

Only the configured Telegram user is allowed to control the workstation.

---

# 🔑 Required Secrets

Configure the following repository secrets:

| Secret | Description |
|----------|-------------|
| `TAILSCALE_AUTH_KEY` | Tailscale authentication key |
| `TELEGRAM_BOT_TOKEN` | Telegram bot token |
| `TELEGRAM_CHAT_ID` | Authorized Telegram user |
| `RDP_PASS` | Your Static Password |
| `GROQ_API_KEY` | Groq API key |
| `CF_TUNNEL_TOKEN` | Cloudflare Tokens for Domain |

---

# 🚀 Getting Started

1. Fork this repository
2. Add all required GitHub Secrets
3. Commit the workflow
4. Open **Actions**
5. Run **RDP-v5.0 Azure Workstation**
6. Wait for provisioning
7. Receive connection details through Telegram
8. Connect via:
   - Tailscale
   - SSH
   - RDP
   - Guacamole
   - Cloudflare Tunnel

---

# 🏗️ Infrastructure Overview

```text
GitHub Actions
       │
       ▼
 Windows Runner
       │
 ├── RDP
 ├── SSH
 ├── Tailscale
 ├── Cloudflare Tunnel
 ├── Docker
 ├── WSL
 ├── Guacamole
 └── Telegram Bot
          │
          ▼
      Groq AI
```

---

# ⚠️ Disclaimer

This project is intended for development, testing, automation, educational, and remote administration purposes.

Users are responsible for complying with:

- GitHub Actions Terms of Service
- Tailscale Policies
- Cloudflare Policies
- Local regulations and applicable laws

---

## ❤️ Built for Remote Workstation Automation

Spin up a cloud workstation in minutes, manage it from Telegram, access it through Tailscale, and tear it down when you're done.
