# 🟩 Kostenloser Minecraft-Server auf GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ Diese Anleitung dient ausschließlich Lehr- und Privatzwecken. Ein 24/7-Betrieb in Codespaces verstößt gegen die GitHub-Nutzungsbedingungen. Das Anti-Sleep-Skript verhindert nur Unterbrechungen *während* einer Spielsitzung, innerhalb des 60-Stunden-Kontingents. Sonst klopft ein gewisser Git um 3 Uhr morgens an deine Tür...

---

## 📋 Inhaltsverzeichnis

- [Was wir tun werden](#-was-wir-tun-werden)
- [Was du brauchst](#-was-du-brauchst)
- [Schritt 0 - Die Werkzeuge verstehen](#-schritt-0--die-werkzeuge-verstehen)
- [Schritt 1 - Die Konten erstellen](#-schritt-1--die-konten-erstellen)
- [Schritt 2 - Repository und Codespace erstellen](#-schritt-2--repository-und-codespace-erstellen)
- [Schritt 3 - Orientierung im Terminal](#-schritt-3--orientierung-im-terminal)
- [Schritt 4 - Java 21 LTS installieren](#-schritt-4--java-21-lts-installieren)
- [Schritt 5 - Python 3 und pip installieren](#-schritt-5--python-3-und-pip-installieren)
- [Schritt 6 - PaperMC herunterladen und einrichten](#-schritt-6--papermc-herunterladen-und-einrichten)
- [Schritt 7 - Playit.gg konfigurieren](#-schritt-7--playitgg-konfigurieren)
- [Schritt 8 - Crafty Controller installieren](#-schritt-8--crafty-controller-installieren)
- [Schritt 9 - Server zu Crafty hinzufügen](#-schritt-9--server-zu-crafty-hinzufügen)
- [Schritt 10 - Anti-Sleep-Skript](#-schritt-10--anti-sleep-skript)
- [Schritt 11 - Automatische Backups](#-schritt-11--automatische-backups)
- [🟢 Eine Sitzung starten](#-eine-sitzung-starten)
- [🔴 Eine Sitzung beenden](#-eine-sitzung-beenden)
- [Fehlerbehebung](#-fehlerbehebung)
- [Kontingent überwachen](#-kontingent-überwachen)

---

## 🎯 Was wir tun werden

Die kostenlosen GitHub Codespaces-Guthaben nutzen, um einen Minecraft-Server in der Cloud zu betreiben, ihn über eine Weboberfläche (Crafty Controller) zu verwalten und durch Playit.gg für Freunde übers Internet erreichbar zu machen – ohne den Router anfassen zu müssen.

Keine Vorkenntnisse nötig. Jeder Befehl wird erklärt.

---

## 🧰 Was du brauchst

Alles ist kostenlos.

| | Element | Details |
|---|---|---|
| 🌐 | Ein Webbrowser | Chrome, Firefox, Edge |
| 📧 | Eine E-Mail-Adresse | Zum Erstellen der beiden Konten |
| 🐙 | Ein GitHub-Konto | Erstellt in Schritt 1 |
| 🎮 | Ein Playit.gg-Konto | Erstellt in Schritt 1 |
| ⏱️ | ~45 Minuten | Für die erste Installation |

> 💡 Einmal eingerichtet, dauert der Neustart des Servers für eine neue Sitzung weniger als 3 Minuten.

---

## 🔍 Schritt 0  Die Werkzeuge verstehen

Fünf Minuten Lesezeit jetzt ersparen dir später viel Verwirrung.

| Werkzeug | Rolle |
|---|---|
| **GitHub Codespaces** | Ein Linux-Computer in der Cloud, zugänglich über den Browser. Die kostenlose Stufe bietet **120 Kernstunden/Monat** → mit der 2-Kern-Maschine sind das **60 echte Spielstunden**. |
| **PaperMC** | Die Server-Engine. Eine verbesserte Version der offiziellen Mojang-Software: flüssiger, weniger Lag, Plugin-kompatibel. |
| **Playit.gg** | Der Tunnel. GitHub vergibt keine öffentliche IP. Playit.gg erstellt eine (`meinserver.playit.gg`), die Freunde direkt in Minecraft eingeben. |
| **Crafty Controller** | Das Web-Bedienfeld. Server per Knopfdruck starten, stoppen, überwachen. |

---

## 👤 Schritt 1  Die Konten erstellen

### 🐙 GitHub

1. Gehe zu [github.com/signup](https://github.com/signup)
2. Gib E-Mail, Passwort und Nutzernamen ein
3. Löse das Puzzle → **Create account**
4. Hole den 6-stelligen Code aus deinem Posteingang und gib ihn ein

✅ Du siehst deinen Nutzernamen oben rechts im GitHub-Dashboard.

### 🎮 Playit.gg

1. Gehe zu [playit.gg](https://playit.gg)
2. **Login** → am Ende des Formulars → **Sign up**
3. Felder ausfüllen und bestätigen
4. Klicke auf den Bestätigungslink, den du per E-Mail erhalten hast

✅ Du kannst auf dein Playit.gg-Dashboard zugreifen.

---

## 🏗️ Schritt 2  Repository und Codespace erstellen

### Das Repository

Ein Repository ist ein Projektordner auf GitHub. Es dient als Grundlage für den Codespace.

1. Auf GitHub: **`+`** oben rechts → **New repository**
2. Ausfüllen:
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ Du befindest dich auf der Seite deines `mc-server`-Repository.

### Der Codespace

> ⚠️ **Kritischer Schritt** – die Maschinenwahl bestimmt dein Kontingent. Ein Fehler hier halbiert es.

1. **`Menü`** → Tab **Codespaces**
2. Oben rechts auf **New Codespace** klicken
3. Wähle das für den Minecraft-Server erstellte Repository
4. Wähle die Region, die dir am nächsten ist (verringert den Ping zwischen dir und dem Server)
5. **Machine type** → **`2-core`** (8 GB RAM) – nicht 4-core wählen
6. **Create codespace** → warte 2-3 Minuten

Ein VS Code-Editor öffnet sich im Browser mit einem Terminal unten.

✅ Du siehst die Eingabeaufforderung im Terminal.

---

## 💻 Schritt 3  Orientierung im Terminal

Das Terminal ist der Ort, an dem du Befehle eingibst. Kopiere einfach, was die Anleitung vorgibt.

| Befehl | Funktion |
|---|---|
| `cd ~` | Zurück zum Home-Ordner |
| `cd ~/minecraft-server` | In den Serverordner wechseln |
| `pwd` | Anzeigen, wo du dich befindest |
| `mkdir -p name` | Einen Ordner erstellen |
| `ls` | Dateien auflisten |
| `sudo` | Als Administrator ausführen |

> 💡 **Goldene Regel:** Jeder Schritt dieser Anleitung gibt an, von welchem Ordner aus der Befehl ausgeführt werden soll. Im Zweifel `pwd` tippen.

---

## ☕ Schritt 4  Java 21 (LTS) installieren

Minecraft ist in Java geschrieben. Version **21** ist die von PaperMC empfohlene. Es ist die **LTS**-Version (Long-Term Support): die stabilste und am längsten gewartete. Neuere Versionen existieren, sind aber keine LTS.

📍 *Aus einem beliebigen Ordner.*

Zuerst prüfen, ob Java bereits vorhanden ist:

    java -version

🔵 Wenn du `openjdk version "21.0.x"` siehst → weiter zu Schritt 5.

Andernfalls:

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ Der Befehl zeigt `openjdk version "21.0.x"`.

---

## 🐍 Schritt 5  Python 3 und pip installieren

Crafty Controller ist in Python entwickelt. Wir benötigen Python 3 und `pip` (den Paketmanager), um es zu installieren und auszuführen.

📍 *Aus deinem Home-Ordner (`cd ~`).*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ Beide Befehle zeigen eine Versionsnummer ohne Fehler.

---

## 🧱 Schritt 6  PaperMC herunterladen und einrichten

### Ordner erstellen

📍 *Aus deinem Home-Ordner (`cd ~`).*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### jq installieren

`jq` liest die PaperMC-API-Antworten, um automatisch den neuesten stabilen Build zu holen.

    sudo apt install jq -y

### PaperMC herunterladen

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 Wenn der Befehl fehlschlägt, verwende diesen festen Build:
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` zeigt `server.jar` in der Liste.

### Die EULA akzeptieren

> ⚠️ **Rechtliche Verpflichtung.** Mojang verlangt die Zustimmung zur Endbenutzer-Lizenzvereinbarung (EULA) vor jedem Start. Ohne diese Datei startet der Server nicht. Durch Ausführen des folgenden Befehls akzeptierst du die Bedingungen unter [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

    echo "eula=true" > eula.txt

✅ `ls` zeigt `eula.txt` neben `server.jar`.

### Erster Teststart

    java -Xms2G -Xmx4G -jar server.jar --nogui

Warte auf die Meldung `Done!` (1-2 Min), dann stoppen:

    stop

✅ Der Server stoppt sauber und du erhältst die Eingabeaufforderung zurück.

### Startskript erstellen

Diese Parameter heißen *Aikar's Flags*. Von der Community anerkannte Speicheroptimierungen, die Lags deutlich reduzieren.

📍 *Zurück zum Home-Ordner (`cd ~`).*

    nano start.sh

Einfügen:

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

Speichern: **Ctrl+X** → **Y** → **Enter**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` zeigt `-rwxr-xr-x` am Zeilenanfang.

---

## 📡 Schritt 7  Playit.gg konfigurieren

Dein Codespace hat keine öffentliche IP. Playit.gg erstellt einen Tunnel und stellt eine Adresse bereit, die Freunde direkt in Minecraft eingeben. Keine Netzwerkkonfiguration deinerseits.

📍 *Aus deinem Home-Ordner (`cd ~`).*

### Agent installieren

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### Agent mit Konto verknüpfen

    playit

Im Terminal erscheint ein Authentifizierungslink. Im Browser öffnen → anmelden → **Claim Agent**. Zurück zum Terminal → **Ctrl+C** → im Hintergrund neu starten:

    playit &

### Tunnel erstellen

1. Auf [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Ausfüllen:
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MeinServer`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 Die öffentliche Adresse wird angezeigt (z. B. `meinserver.playit.gg:12345`). **Notieren. Das gibst du an Freunde weiter.**

✅ Der Tunnel erscheint im Dashboard mit dem Status "Connected".

---

## 🎛️ Schritt 8  Crafty Controller installieren

Crafty Controller ist ein Web-Bedienfeld: Starten, Stoppen, Logs anzeigen, Spieler verwalten – alles ohne Kommandozeile.

📍 *Aus deinem Home-Ordner (`cd ~`).*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

Das Skript stellt ein paar Fragen:

| Frage | Antwort |
|---|---|
| Port | **Enter** drücken (behält `8443`) |
| Benutzer | `crafty` |
| Admin-Passwort | Eins wählen und **aufschreiben** |
| Bestätigung | `y` |

Die Installation dauert 3-5 Minuten.

### Crafty starten

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### Oberfläche erreichbar machen

1. VS Code → Tab **PORTS** unten
2. Falls `8443` nicht erscheint → **Add Port** → `8443` → bestätigen
3. Rechtsklick auf `8443` → **Port Visibility** → **Public**
4. Generierte URL in neuem Tab öffnen
5. Sicherheitswarnung → **Erweitert** → **Fortfahren**
6. Anmelden: `admin` + dein Passwort

✅ Du befindest dich auf dem Crafty Controller-Dashboard.

---

## 🔗 Schritt 9  Server zu Crafty hinzufügen

**Servers** → **Create Server** → ausfüllen:

| Feld | Wert |
|---|---|
| Server Name | `MeinServer` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 Beim allerersten Start zeigt Crafty möglicherweise ein Pop-up zur Annahme der EULA. Klicke auf **I Accept** und starte dann neu.

✅ Der Server wechselt in den Status "Running" (grün).

---

## ⏳ Schritt 10  Anti-Sleep-Skript

Ein Codespace stoppt automatisch nach 30 Minuten Inaktivität. Dieses Skript sendet alle 10 Minuten ein Signal, um die Sitzung während der Spielzeit aktiv zu halten.

📍 *Aus deinem Home-Ordner (`cd ~`).*

    nano keep-alive.sh

Einfügen:

    #!/bin/bash
    # Keep-alive für GitHub Codespaces
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Enter**, dann:

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` verhindert, dass das Skript stoppt, wenn die Sitzung geschlossen wird. `&` führt es im Hintergrund aus.

✅ Nach ein paar Minuten zeigt `cat ~/keep-alive.log` Zeitstempel-Zeilen.

---

## 💾 Schritt 11  Automatische Backups

Dieses Skript erstellt stündlich ein komprimiertes Archiv deiner Welt. Im Falle einer Beschädigung kannst du auf eine aktuelle Sicherung zurückgreifen.

📍 *Aus deinem Home-Ordner (`cd ~`).*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

Einfügen:

    #!/bin/bash
    # Automatisches Backup der Minecraft-Welt
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - Backup abgeschlossen." >> ~/backup.log

**Ctrl+X** → **Y** → **Enter**, dann:

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` zeigt die geplante Zeile.

---

## 🟢 Eine Sitzung starten

> 📌 Bei jedem Öffnen des Codespace diese 4 Befehle in dieser Reihenfolge in das Terminal kopieren und einfügen.

    # 1. Anti-Sleep
    nohup ~/keep-alive.sh &

    # 2. Playit.gg-Tunnel
    playit &

    # 3. Minecraft-Server
    cd ~/minecraft-server && ~/start.sh &

    # 4. Crafty-Oberfläche
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

1-2 Minuten warten → "Running" in Crafty prüfen → Playit.gg-Adresse an Freunde weitergeben. 🎮

---

## 🔴 Eine Sitzung beenden

> ⚠️ **Den Tab zu schließen reicht nicht.** Der Codespace läuft im Hintergrund weiter und verbraucht dein Kontingent. Folge diesen Schritten am Ende jeder Sitzung.

**1. Minecraft-Server stoppen**

Über Crafty: ⏹️-Button in der Oberfläche klicken.

Über das Terminal:

    kill $(pgrep -f "server.jar")

**2. Hintergrundprozesse beenden**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Codespace stoppen** ← wichtigster Schritt

Über GitHub (empfohlen):
1. [github.com/codespaces](https://github.com/codespaces)
2. Deinen aktiven Codespace (🟢 grüner Punkt)
3. **`...`** → **Stop codespace**

Über den Editor: unten links → Codespace-Name → **Stop Current Codespace**

✅ Der grüne Punkt wird grau. Der Codespace ist gestoppt.

---

## 🆘 Fehlerbehebung

| Symptom | Lösung |
|---|---|
| ❌ `java -version` zeigt nicht `21.x` | Schritt 4 von Anfang wiederholen |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` bei `.sh` | `chmod +x skriptname.sh` |
| ❌ Server startet nicht (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ Playit.gg-Adresse funktioniert nicht | `ps aux \| grep playit` → falls nicht vorhanden: `playit &` |
| ❌ Crafty nicht erreichbar (Port 8443) | Tab **PORTS** → Rechtsklick `8443` → **Port Visibility** → **Public** |
| ❌ Codespace stoppt mitten im Spiel | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y`, dann Download erneut versuchen |
| ❌ `OutOfMemoryError` in Logs | Prüfen, ob die Maschine **2-core / 8 GB RAM** ist |

Bei anderen Problemen: Kopiere die genaue Fehlermeldung auf [Stack Overflow](https://stackoverflow.com) mit dem Tag `[minecraft]` oder `[github-codespaces]`. Communities: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 Kontingent überwachen

GitHub bietet **120 kostenlose Kernstunden pro Monat**. Mit der 2-Kern-Maschine verbraucht jede Spielstunde 2 → **60 echte Stunden pro Monat**.

So siehst du deinen Verbrauch: **GitHub-Avatar** → **Settings** → **Billing & plans** → **Usage this month** → Zeile **Codespaces**

> ⚠️ Wenn du dich 120 Kernstunden näherst, stoppe den Codespace sofort und warte auf die monatliche Erneuerung.

---

## 📎 Ressourcen

- [PaperMC Dokumentation](https://docs.papermc.io)
- [Crafty Controller Dokumentation](https://docs.craftycontrol.com)
- [Playit.gg Dokumentation](https://playit.gg/support)
- [GitHub Codespaces Dokumentation](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*Getestet auf einem frisch erstellten Codespace - Mai 2026.*
