8GB/256GB

# Setup
## 1. Clean macOS Start
- shut down
- hold power
- options -> disk utility -> erase -> reinstall macOS
## 2. Power & Efficiency Config
- System settings -> displays -> advanced -> toggle on "prevent automatic sleeping when the display is off."
- system settings -> energy saver -> turn on "wake for network access" and "start up automatically after a power failure"
## 3. LAN Access (Main PC via Ethernet)
- system settings -> general -> sharing
	- toggle on "screen sharing" and "remote login"
- Main PC
	- VNC viewer (like RealVNC)
	- PuTTY/Windows Terminal to SSH
## 4. Remote Access (Phone/Outside network)
- install Tailscale on the Mac Mini, your phone, and your Main PC

# OpenClaw

## Control
- Webui

## Security
```
openclaw security audit --fix
```
### Telegram
```
openclaw config set channels.telegram.dmPolicy "allowlist"
openclaw config set channels.telegram.allowFrom '["YOUR_USER_ID"]'
```

## Name
Zilizum

## Local AI model
- Ollama: llama3.2:3b