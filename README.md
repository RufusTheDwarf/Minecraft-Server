# ⛏️ Free Minecraft Server - GitHub Codespaces

> **Zero euros. Zero installation. Zero hassle.**  
> A high‑performance Minecraft server in the cloud, up and running in under an hour.

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/Server-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/Panel-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/Tunnel-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![MIT License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ Overview

This repository is a **complete, step‑by‑step, and fully verified guide** for hosting your very own Minecraft server **free of charge** on GitHub Codespaces.

You and your friends can play together on a powerful server, accessible from anywhere in the world **without spending a single penny**, all while staying within GitHub’s free quotas.

    Web browser → GitHub Codespace (Linux) → PaperMC → Playit.gg → Your friends 🎮

**What you get:**
- 🖥️ **Linux virtual machine** in the cloud (2 cores, 8 GB RAM, 32 GB storage)
- 🟢 **PaperMC** - the most optimised and stable Minecraft server on the market
- 🧭 **Crafty Controller** - a web panel to manage the server in just a few clicks
- 🌐 **Playit.gg** - a public tunnel so your friends can connect without any network configuration
- 💾 **Automatic backups** and an **anti‑sleep script** included

---

## 🎯 Who is this for?

**Everyone.** This guide is written in an educational and reassuring way.

| Your profile | Is this guide right for you? |
|---|---|
| Complete beginner, never touched Linux | ✅ Yes - everything is explained and justified |
| Comfortable with the terminal | ✅ Yes - skip straight to the essentials |
| No experience with networking or server administration | ✅ Yes - Playit.gg handles that for you |
| No budget | ✅ Yes - 100 % free within the quotas |

> If you can **copy‑paste** and **follow instructions**, you can create this server.

---

## ⚡ Prerequisites

All you need:

- [ ] A **web browser** (Chrome, Firefox, Edge…)
- [ ] A free **GitHub account** - [sign up here](https://github.com/signup)
- [ ] A free **Playit.gg account** - [sign up here](https://playit.gg)

**No software to install on your machine.**

---

## 📂 Repository files (Coming soon)

⚠️ This section is currently under construction.  
The information below is only a preview.  
See the guide in the [`Docs`](Docs) folder.

| File | Purpose |
|---|---|
| `README.md` | This file - project overview |
| `GUIDE.md` | 📘 **The complete guide**, step by step |
| `start.sh` | Launches the server with Aikar’s Flags optimisations |
| `keep-alive.sh` | Prevents the Codespace from automatically sleeping |
| `backup.sh` | Automatic backup of the Minecraft world |

---

## 🚀 Quick start (Coming soon)

⚠️ This section is currently under construction.  
The information below is only a preview.  
See the guide in the [`Docs`](Docs) folder.

    # 1. Clone this repository into a GitHub Codespace
    # 2. Install Java 21
    sudo apt-get install -y openjdk-21-jdk

    # 3. Start the server
    bash start.sh

    # 4. Start the Playit.gg tunnel (in a second terminal)
    ./playit

    # 5. Open Crafty Controller on port 8443

> **For the detailed guide, see [`EN_GUIDE.md`](Docs/EN_Guide.md).**

---

## 🗂️ Guide contents

The `EN_GUIDE.md` file covers the following 17 steps:

1. Introduction and required hardware
2. Understanding the tools (Codespaces, PaperMC, Crafty, Playit.gg)
3. Creating GitHub and Playit.gg accounts
4. Creating the repository and Codespace
5. Getting comfortable with the Linux terminal
6. Installing Java 21
7. Installing Python 3 and pip
8. Downloading and configuring PaperMC
9. Configuring Playit.gg
10. Installing Crafty Controller
11. Adding the server to Crafty
12. Anti‑sleep script (keep‑alive)
13. Automatic backups
14. ✅ Session start checklist
15. 🛑 Session stop checklist
16. Troubleshooting and support
17. Monthly quota monitoring

Each step includes: the *why*, the exact commands to copy, and a check to make sure everything works.

---

## ⚠️ Limitations & responsible use

### Free GitHub Codespaces quota

    120 core‑hours / month  →  60 hours of play on a 2‑core machine

| Do | Don’t |
|---|---|
| ✅ Stop the Codespace after each session | ❌ Leave it running 24/7 |
| ✅ Check Settings › Billing & plans | ❌ Ignore your usage |
| ✅ Use for occasional sessions | ❌ Use for continuous production |

> ⚠️ Running a game server continuously is **not compliant** with the GitHub Codespaces terms of service. This guide is designed for occasional and responsible use.

### Storage
- **32 GB** available on the 2‑core machine
- **Non‑versioned** data is lost if the Codespace is deleted
- Use `backup.sh` and commit your backups regularly

---

## 🤝 Contributing

This guide is carefully maintained, but mistakes happen. Found a typo, an outdated command, or something that could be improved?

1. **Open an [Issue](../../issues)** to report the problem
2. **Submit a [Pull Request](../../pulls)** with your corrections

---

## 💬 Support & Community

| Resource | For |
|---|---|
| [PaperMC Discord](https://discord.gg/papermc) | Questions about the Minecraft server |
| [Playit.gg Discord](https://discord.gg/playit) | Tunnel / network issues |
| [Stack Overflow](https://stackoverflow.com) | Linux / Java errors tagged `[minecraft]` `[github-codespaces]` |
| [GitHub Issues](../../issues) | Problems specific to this guide |

---

## 📄 Licence

Distributed under the **MIT** licence. Free to use, modify and redistribute, provided the copyright notice is retained.

---

<div align="center">

**Ready to play?**

### 👉 [Open the complete guide – EN_Guide.md](Tutorial/🇬🇧En_Guide.md)

*Thanks to the PaperMC, Crafty Controller, Playit.gg and GitHub communities.*

</div>
