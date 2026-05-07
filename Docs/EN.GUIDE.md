# 🟩 Free Minecraft Server on GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ This guide is intended for educational and private use. Running a server 24/7 in Codespaces is not compliant with GitHub's ToS. The anti-sleep script is only meant to prevent disconnections *during* a gaming session, within the 60 h/month quota. Or a certain Git will come knocking at your door at 3 AM...

---

## 📋 Table of Contents

- [What we'll do](#-what-well-do)
- [What you need](#-what-you-need)
- [Step 0 - Understanding the tools](#-step-0--understanding-the-tools)
- [Step 1 - Creating the accounts](#-step-1--creating-the-accounts)
- [Step 2 - Creating the repository and Codespace](#-step-2--creating-the-repository-and-codespace)
- [Step 3 - Getting oriented in the terminal](#-step-3--getting-oriented-in-the-terminal)
- [Step 4 - Installing Java 21 LTS](#-step-4--installing-java-21-lts)
- [Step 5 - Installing Python 3 and pip](#-step-5--installing-python-3-and-pip)
- [Step 6 - Downloading and setting up PaperMC](#-step-6--downloading-and-setting-up-papermc)
- [Step 7 - Configuring Playit.gg](#-step-7--configuring-playitgg)
- [Step 8 - Installing Crafty Controller](#-step-8--installing-crafty-controller)
- [Step 9 - Adding the server to Crafty](#-step-9--adding-the-server-to-crafty)
- [Step 10 - Anti-sleep script](#-step-10--anti-sleep-script)
- [Step 11 - Automatic backups](#-step-11--automatic-backups)
- [🟢 Starting a session](#-starting-a-session)
- [🔴 Stopping a session](#-stopping-a-session)
- [Troubleshooting](#-troubleshooting)
- [Monitoring your quota](#-monitoring-your-quota)

---

## 🎯 What we'll do

Use the free GitHub Codespaces credits to run a Minecraft server in the cloud, manage it via a web interface (Crafty Controller), and make it accessible to your friends over the internet without touching your router, thanks to Playit.gg.

No prior knowledge required. Every command is explained.

---

## 🧰 What you need

Everything is free.

| | Item | Details |
|---|---|---|
| 🌐 | A web browser | Chrome, Firefox, Edge |
| 📧 | An email address | To create the two accounts |
| 🐙 | A GitHub account | Created in Step 1 |
| 🎮 | A Playit.gg account | Created in Step 1 |
| ⏱️ | ~45 minutes | For the first installation |

> 💡 Once set up, restarting the server for a new session takes less than 3 minutes.

---

## 🔍 Step 0  Understanding the tools

Five minutes of reading now will save you a lot of confusion later.

| Tool | Role |
|---|---|
| **GitHub Codespaces** | A Linux computer in the cloud, accessible from your browser. The free tier gives **120 core-hours/month** → with the 2-core machine, that's **60 actual hours of play**. |
| **PaperMC** | The server engine. An improved version of the official Mojang software: smoother, less lag, plugin-compatible. |
| **Playit.gg** | The tunnel. GitHub doesn't give you a public IP. Playit.gg creates one (`myserver.playit.gg`) that your friends enter directly into Minecraft. |
| **Crafty Controller** | The web control panel. Start, stop, and monitor the server with button clicks. |

---

## 👤 Step 1  Creating the accounts

### 🐙 GitHub

1. Go to [github.com/signup](https://github.com/signup)
2. Enter an email, a password, and a username
3. Solve the puzzle → **Create account**
4. Retrieve the 6-digit code from your inbox and enter it

✅ You see your username at the top right of the GitHub dashboard.

### 🎮 Playit.gg

1. Go to [playit.gg](https://playit.gg)
2. **Login** → at the bottom of the form → **Sign up**
3. Fill in the fields and validate
4. Click the confirmation link received by email

✅ You can access your Playit.gg dashboard.

---

## 🏗️ Step 2  Creating the repository and Codespace

### The repository

A repository is a project folder on GitHub. It serves as the base to create the Codespace.

1. On GitHub: **`+`** top right → **New repository**
2. Fill in:
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ You are on the page of your `mc-server` repository.

### The Codespace

> ⚠️ **Critical step** - the machine choice determines your quota. Choosing the wrong one cuts it in half.

1. **`Menu`** → **Codespaces** tab
2. Click top right **New Codespace**
3. Choose the repository you created for the Minecraft server
4. Choose the region closest to you (this reduces the ping between you and the server)
5. **Machine type** → **`2-core`** (8 GB RAM) - do not choose 4-core
6. **Create codespace** → wait 2-3 minutes

A VS Code editor opens in your browser with a terminal at the bottom.

✅ You see the command prompt in the terminal.

---

## 💻 Step 3  Getting oriented in the terminal

The terminal is where you type commands. Simply copy-paste what the guide indicates.

| Command | What it does |
|---|---|
| `cd ~` | Go back to the home folder |
| `cd ~/minecraft-server` | Go to the server folder |
| `pwd` | Show where you are |
| `mkdir -p name` | Create a folder |
| `ls` | List files |
| `sudo` | Run as administrator |

> 💡 **Golden rule:** each step in this guide specifies which folder to run the command from. If in doubt, type `pwd`.

---

## ☕ Step 4  Installing Java 21 (LTS)

Minecraft is written in Java. Version **21** is the one recommended by PaperMC. It is the **LTS** (Long-Term Support) version: the most stable, the longest maintained. Newer versions exist but are not LTS.

📍 *From any folder.*

First, check if Java is already there:

    java -version

🔵 If you see `openjdk version "21.0.x"` → skip to Step 5.

Otherwise:

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ The command displays `openjdk version "21.0.x"`.

---

## 🐍 Step 5  Installing Python 3 and pip

Crafty Controller is developed in Python. We need Python 3 and `pip` (its package manager) to install and run it.

📍 *From your home folder (`cd ~`).*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ Both commands display a version number without error.

---

## 🧱 Step 6  Downloading and setting up PaperMC

### Create the folder

📍 *From your home folder (`cd ~`).*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### Install jq

`jq` reads the PaperMC API responses to automatically fetch the latest stable build.

    sudo apt install jq -y

### Download PaperMC

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 If the command fails, use this fixed build:
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` shows `server.jar` in the list.

### Accept the EULA

> ⚠️ **Legal obligation.** Mojang requires acceptance of the End User License Agreement (EULA) before any startup. Without this file, the server refuses to start. By running the command below, you accept the terms at [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

    echo "eula=true" > eula.txt

✅ `ls` shows `eula.txt` next to `server.jar`.

### First test launch

    java -Xms2G -Xmx4G -jar server.jar --nogui

Wait for the `Done!` message (1-2 min), then stop:

    stop

✅ The server stops cleanly and you get the command prompt back.

### Create the startup script

These parameters are called *Aikar's flags*. Community-recognized memory optimizations for Minecraft that significantly reduce lag.

📍 *Go back to your home folder (`cd ~`).*

    nano start.sh

Paste:

    #!/bin/bash
    cd ~/minecraft-server
    java -Xms4G -Xmx4G \
      -XX:+UseG1GC \
      -XX:+ParallelRefProcEnabled \
      -XX:MaxGCPauseMillis=200 \
      -XX:+UnlockExperimentalVMOptions \
      -XX:+DisableExplicitGC \
      -XX:+AlwaysPreTouch \
      -XX:G1NewSizePercent=40 \
      -XX:G1MaxNewSizePercent=50 \
      -XX:G1HeapRegionSize=16M \
      -XX:G1ReservePercent=15 \
      -XX:G1HeapWastePercent=5 \
      -XX:G1MixedGCCountTarget=4 \
      -XX:InitiatingHeapOccupancyPercent=20 \
      -XX:G1MixedGCLiveThresholdPercent=90 \
      -XX:G1RSetUpdatingPauseTimePercent=5 \
      -XX:SurvivorRatio=32 \
      -XX:+PerfDisableSharedMem \
      -XX:MaxTenuringThreshold=1 \
      -jar server.jar --nogui

Save: **Ctrl+X** → **Y** → **Enter**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` shows `-rwxr-xr-x` at the start of the line.

---

## 📡 Step 7  Configuring Playit.gg

Your Codespace has no public IP address. Playit.gg creates a tunnel and provides you with an address your friends enter directly into Minecraft. No network configuration on your side.

📍 *From your home folder (`cd ~`).*

### Install the agent

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### Link the agent to your account

    playit

An authentication link appears in the terminal. Open it in your browser → log in → **Claim Agent**. Return to the terminal → **Ctrl+C** → rerun in background:

    playit &

### Create the tunnel

1. On [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Fill in:
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MyServer`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 The public address is displayed (e.g. `myserver.playit.gg:12345`). **Note it down. This is what you give to your friends.**

✅ The tunnel appears in the dashboard with "Connected" status.

---

## 🎛️ Step 8  Installing Crafty Controller

Crafty Controller is a web control panel: start, stop, view logs, manage players from an interface, no command line needed.

📍 *From your home folder (`cd ~`).*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

The script asks a few questions:

| Question | Answer |
|---|---|
| Port | Press **Enter** (keeps `8443`) |
| User | `crafty` |
| Admin password | Choose one and **write it down** |
| Confirmation | `y` |

Installation takes 3-5 minutes.

### Start Crafty

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### Make the interface accessible

1. VS Code → **PORTS** tab at the bottom
2. If `8443` doesn't appear → **Add Port** → `8443` → validate
3. Right-click on `8443` → **Port Visibility** → **Public**
4. Open the generated URL in a new tab
5. Security warning → **Advanced** → **Proceed**
6. Log in: `admin` + your password

✅ You are on the Crafty Controller dashboard.

---

## 🔗 Step 9  Adding the server to Crafty

**Servers** → **Create Server** → fill in:

| Field | Value |
|---|---|
| Server Name | `MyServer` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 On the very first start, Crafty may show a pop-up to accept the EULA. Click **I Accept** and then restart.

✅ The server goes to "Running" status (green) in the interface.

---

## ⏳ Step 10  Anti-sleep script

A Codespace automatically stops after 30 minutes of inactivity. This script sends a signal every 10 minutes to keep the session active during your play sessions.

📍 *From your home folder (`cd ~`).*

    nano keep-alive.sh

Paste:

    #!/bin/bash
    # Keep-alive for GitHub Codespaces
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Enter**, then:

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` prevents the script from stopping if your session closes. `&` runs it in the background.

✅ After a few minutes, `cat ~/keep-alive.log` shows timestamped lines.

---

## 💾 Step 11  Automatic backups

This script creates a compressed archive of your world every hour. In case of corruption, you can revert to a recent backup.

📍 *From your home folder (`cd ~`).*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

Paste:

    #!/bin/bash
    # Automatic backup of the Minecraft world
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - Backup completed." >> ~/backup.log

**Ctrl+X** → **Y** → **Enter**, then:

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` shows the scheduled line.

---

## 🟢 Starting a session

> 📌 Every time you open the Codespace, copy-paste these 4 commands in the terminal in this order.

    # 1. Anti-sleep
    nohup ~/keep-alive.sh &

    # 2. Playit.gg tunnel
    playit &

    # 3. Minecraft server
    cd ~/minecraft-server && ~/start.sh &

    # 4. Crafty interface
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

Wait 1-2 minutes → check "Running" in Crafty → give the Playit.gg address to your friends. 🎮

---

## 🔴 Stopping a session

> ⚠️ **Closing the tab isn't enough.** The Codespace keeps running in the background and consumes your quota. Follow these steps at the end of every session.

**1. Stop the Minecraft server**

Via Crafty: click the ⏹️ button in the interface.

Via the terminal:

    kill $(pgrep -f "server.jar")

**2. Stop background processes**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Stop the Codespace** ← most important step

From GitHub (recommended):
1. [github.com/codespaces](https://github.com/codespaces)
2. Your active Codespace (🟢 green dot)
3. **`...`** → **Stop codespace**

From the editor: bottom left → Codespace name → **Stop Current Codespace**

✅ The green dot turns gray. The Codespace is stopped.

---

## 🆘 Troubleshooting

| Symptom | Solution |
|---|---|
| ❌ `java -version` doesn't show `21.x` | Redo Step 4 from the beginning |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` on a `.sh` | `chmod +x script_name.sh` |
| ❌ Server refuses to start (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ Playit.gg address doesn't work | `ps aux \| grep playit` → if missing, relaunch: `playit &` |
| ❌ Crafty unreachable (port 8443) | **PORTS** tab → right-click `8443` → **Port Visibility** → **Public** |
| ❌ Codespace stops mid-game | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` then retry the download |
| ❌ `OutOfMemoryError` in logs | Check that the machine is indeed **2-core / 8 GB RAM** |

For any other issue: copy the exact error message to [Stack Overflow](https://stackoverflow.com) with the `[minecraft]` or `[github-codespaces]` tag. Communities: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 Monitoring your quota

GitHub offers **120 free core-hours per month**. With the 2-core machine, each hour of play consumes 2 → **60 actual hours per month**.

To see your usage: **GitHub avatar** → **Settings** → **Billing & plans** → **Usage this month** → **Codespaces** line

> ⚠️ If you approach 120 core-hours, stop the Codespace immediately and wait for the monthly renewal.

---

## 📎 Resources

- [PaperMC Documentation](https://docs.papermc.io)
- [Crafty Controller Documentation](https://docs.craftycontrol.com)
- [Playit.gg Documentation](https://playit.gg/support)
- [GitHub Codespaces Documentation](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*Tested on a freshly created Codespace - May 2026.*
