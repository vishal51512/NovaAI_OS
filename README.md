# 🚀 NovaAI OS

NovaAI OS is a **custom Linux-based operating system** built from scratch with a **terminal-first user interface** and **integrated AI interaction**.  
It is designed as an **AI-first, minimal, and educational OS**, focusing on clarity, control, and low-level system understanding.

This project demonstrates kernel customization, init system design, userspace construction, and OS-level AI integration.

---

## ✨ Key Features

- 🔧 Custom Linux kernel
- 🧩 Custom init system (PID 1)
- 📦 BusyBox-based minimal userspace
- 🖥️ Terminal-first UI (no X11 / Wayland)
- 📊 Live system monitoring (CPU, memory, uptime)
- 🤖 Integrated AI interaction (`nova ask`)
- 🧠 Plugin-based command system (`/help`, `/status`, etc.)
- 📜 Scrolling chat history
- 💿 Bootable ISO image

---

## 🧠 Architecture Overview

Kernel
└── init (custom PID 1)
├── novad (Nova system daemon)
└── nova-tui (Terminal UI)
├── System stats
├── AI interaction
└── Plugin commands


---

## 🖥️ Nova Terminal UI

The system boots **directly into Nova TUI**, not a shell.

Example interface:

Nova Chat:
Hello! How can I help you today?

Ask Nova:

### Supported Commands

| Command | Description |
|-------|-------------|
| `/help` | Show available commands |
| `/status` | Show CPU and memory usage |
| `/uptime` | Show system uptime |
| `/clear` | Clear chat history |
| `q` | Exit OS |

---

## 🛠️ Build Components

- **Kernel:** Custom Linux build
- **Userspace:** BusyBox
- **Initramfs:** Custom-built
- **UI:** ANSI-based TUI written in C
- **AI Backend:** Nova daemon (`nova ask`)
- **Bootloader:** GRUB
- **Distribution:** Bootable ISO

---

## 💿 Booting the OS

### Using QEMU

```bash
qemu-system-x86_64 \
  -cdrom NovaAI-OS.iso \
  -m 1024

