# ⛏️ Kostenloser Minecraft-Server - GitHub Codespaces

> **Null Euro. Null Installation. Null Stress.**  
> Ein leistungsstarker Minecraft-Server in der Cloud, einsatzbereit in weniger als einer Stunde.

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/Server-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/Panel-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/Tunnel-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![MIT-Lizenz](https://img.shields.io/badge/Lizenz-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ Überblick

Dieses Repository ist eine **vollständige, schrittweise und vollständig geprüfte Anleitung**, um deinen eigenen Minecraft-Server **kostenlos** auf GitHub Codespaces zu hosten.

Du und deine Freunde könnt gemeinsam auf einem leistungsstarken Server spielen, der von überall auf der Welt erreichbar ist - **ohne einen Cent auszugeben** und innerhalb der kostenlosen Kontingente von GitHub.

    Webbrowser → GitHub Codespace (Linux) → PaperMC → Playit.gg → Deine Freunde 🎮

**Das bekommst du:**
- 🖥️ **Linux-VM** in der Cloud (2 Kerne, 8 GB RAM, 32 GB Speicher)
- 🟢 **PaperMC** - der optimierteste und stabilste Minecraft-Server auf dem Markt
- 🧭 **Crafty Controller** - Web‑Panel zur Serververwaltung mit wenigen Klicks
- 🌐 **Playit.gg** - öffentlicher Tunnel, damit Freunde ohne Netzwerkkonfiguration beitreten können
- 💾 **Automatische Backups** und **Anti‑Sleep‑Skript** inklusive

---

## 🎯 Für wen?

**Für jeden.** Diese Anleitung ist pädagogisch und verständlich geschrieben.

| Dein Profil | Ist diese Anleitung geeignet? |
|---|---|
| Kompletter Anfänger, noch nie Linux benutzt | ✅ Ja - alles wird erklärt und begründet |
| Vertraut mit dem Terminal | ✅ Ja - spring direkt zum Wesentlichen |
| Keine Erfahrung mit Netzwerk oder Administration | ✅ Ja - Playit.gg übernimmt das für dich |
| Kein Budget | ✅ Ja - 100 % kostenlos innerhalb der Kontingente |

> Wenn du **kopieren und einfügen** sowie **Anweisungen befolgen** kannst, kannst du diesen Server erstellen.

---

## ⚡ Voraussetzungen

Du brauchst nur:

- [ ] Einen **Webbrowser** (Chrome, Firefox, Edge…)
- [ ] Ein kostenloses **GitHub-Konto** - [hier registrieren](https://github.com/signup)
- [ ] Ein kostenloses **Playit.gg-Konto**  [hier registrieren](https://playit.gg)

**Keine Software-Installation auf deinem Rechner nötig.**

---

## 📂 Dateien im Repository (In Kürze)

⚠️ Dieser Abschnitt befindet sich noch im Aufbau.  
Die folgenden Angaben sind nur Vorschauen.  
Siehe die Anleitung im Ordner [`Docs`](../Docs).

| Datei | Zweck |
|---|---|
| `README.md` | Diese Datei - Projektüberblick |
| `GUIDE.md` | 📘 **Die vollständige Anleitung**, Schritt für Schritt |
| `start.sh` | Startet den Server mit den Aikar‑Optimierungen (Flags) |
| `keep-alive.sh` | Verhindert das automatische Einschlafen des Codespace |
| `backup.sh` | Automatisches Backup der Minecraft-Welt |

---

## 🚀 Schnellstart (In Kürze)

⚠️ Dieser Abschnitt befindet sich noch im Aufbau.  
Die folgenden Angaben sind nur Vorschauen.  
Siehe die Anleitung im Ordner [`Docs`](../Docs).

    # 1. Klone dieses Repository in einen GitHub Codespace
    # 2. Installiere Java 21
    sudo apt-get install -y openjdk-21-jdk

    # 3. Starte den Server
    bash start.sh

    # 4. Starte den Playit.gg-Tunnel (in einem zweiten Terminal)
    ./playit

    # 5. Öffne Crafty Controller auf Port 8443

> **Für die ausführliche Anleitung siehe [`DE_GUIDE.md`](../Docs/DE_Guide.md).**

---

## 🗂️ Inhalt der Anleitung

Die Datei `DE_GUIDE.md` deckt die folgenden 17 Schritte ab:

1. Einführung und benötigte Hardware
2. Die Werkzeuge verstehen (Codespaces, PaperMC, Crafty, Playit.gg)
3. GitHub- und Playit.gg-Konten erstellen
4. Repository und Codespace anlegen
5. Umgang mit dem Linux‑Terminal
6. Java 21 installieren
7. Python 3 und pip installieren
8. PaperMC herunterladen und konfigurieren
9. Playit.gg konfigurieren
10. Crafty Controller installieren
11. Server zu Crafty hinzufügen
12. Anti‑Sleep‑Skript (keep‑alive)
13. Automatische Backups
14. ✅ Checkliste für den Session-Start
15. 🛑 Checkliste für das Session-Ende
16. Fehlerbehebung und Support
17. Überwachung des monatlichen Kontingents

Jeder Schritt enthält: die Erklärung des *Warum*, die exakten Befehle zum Kopieren und eine Kontrolle, ob alles funktioniert.

---

## ⚠️ Einschränkungen & verantwortungsvolle Nutzung

### Kostenloses GitHub Codespaces-Kontingent

    120 Kernstunden / Monat  →  60 Spielstunden auf einer 2‑Kern‑Maschine

| Tun | Vermeiden |
|---|---|
| ✅ Codespace nach jeder Sitzung beenden | ❌ 24/7 laufen lassen |
| ✅ Settings › Billing & plans kontrollieren | ❌ Den Verbrauch ignorieren |
| ✅ Für gelegentliche Sitzungen nutzen | ❌ Dauerhaften Produktivbetrieb |

> ⚠️ Ein dauerhaft laufender Spieleserver ist **nicht konform** mit den Nutzungsbedingungen von GitHub Codespaces. Diese Anleitung ist für gelegentliche und verantwortungsvolle Nutzung gedacht.

### Speicher
- **32 GB** auf der 2‑Kern‑Maschine verfügbar
- **Nicht versionierte** Daten gehen beim Löschen des Codespace verloren
- Nutze `backup.sh` und committe regelmäßig deine Backups

---

## 🤝 Mitwirken

Diese Anleitung wird sorgfältig gepflegt, aber Fehler passieren. Ein Tippfehler, ein veralteter Befehl oder etwas, das verbessert werden kann?

1. **Erstelle ein [Issue](../../../issues)**, um das Problem zu melden
2. **Reiche einen [Pull Request](../../../pulls)** mit deinen Korrekturen ein

---

## 💬 Support & Community

| Ressource | Für |
|---|---|
| [PaperMC Discord](https://discord.gg/papermc) | Fragen zum Minecraft-Server |
| [Playit.gg Discord](https://discord.gg/playit) | Tunnel‑ / Netzwerkprobleme |
| [Stack Overflow](https://stackoverflow.com) | Linux‑ / Java‑Fehler mit Tags `[minecraft]` `[github-codespaces]` |
| [GitHub Issues](../../../issues) | Spezifische Probleme mit dieser Anleitung |

---

## 📄 Lizenz

Verteilt unter der **MIT-Lizenz**. Freie Nutzung, Änderung und Weitergabe unter Beibehaltung des Urheberrechtshinweises.

---

<div align="center">

**Bereit zum Spielen?**

### 👉 [Vollständige Anleitung öffnen - DE_Guide.md](Tutorial/🇩🇪De_Guide.md)

*Danke an die Communities PaperMC, Crafty Controller, Playit.gg und GitHub.*

</div>
