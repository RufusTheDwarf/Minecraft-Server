# ⛏️ Server Minecraft Gratuito - GitHub Codespaces

> **Zero euro. Zero installazione. Zero pensieri.**  
> Un server Minecraft performante nel cloud, operativo in meno di un’ora.

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/Server-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/Pannello-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/Tunnel-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![Licenza MIT](https://img.shields.io/badge/Licenza-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ Panoramica

Questo repository è una **guida completa, passo dopo passo e interamente verificata** per ospitare il tuo server Minecraft **gratuitamente** su GitHub Codespaces.

Tu e i tuoi amici potete giocare insieme su un server potente, accessibile da qualsiasi parte del mondo **senza spendere un centesimo**, rimanendo nei limiti gratuiti di GitHub.

    Browser web → GitHub Codespace (Linux) → PaperMC → Playit.gg → I tuoi amici 🎮

**Cosa ottieni:**
- 🖥️ **Macchina virtuale Linux** nel cloud (2 core, 8 GB RAM, 32 GB storage)
- 🟢 **PaperMC** - il server Minecraft più ottimizzato e stabile sul mercato
- 🧭 **Crafty Controller** - pannello web per gestire il server in pochi clic
- 🌐 **Playit.gg** - tunnel pubblico per connettere gli amici senza configurazione di rete
- 💾 **Backup automatici** e **script anti‑sospensione** inclusi

---

## 🎯 A chi è rivolto?

**A tutti.** Questa guida è scritta in modo chiaro e rassicurante.

| Il tuo profilo | Questa guida fa per te? |
|---|---|
| Principiante assoluto, mai usato Linux | ✅ Sì - tutto è spiegato e motivato |
| Esperto del terminale | ✅ Sì - vai direttamente all’essenziale |
| Nessuna esperienza di rete o amministrazione | ✅ Sì - Playit.gg se ne occupa per te |
| Senza budget | ✅ Sì - 100% gratuito entro i limiti |

> Se sai fare **copia‑incolla** e **seguire le istruzioni**, puoi creare questo server.

---

## ⚡ Prerequisiti

Ti servono solo:

- [ ] Un **browser web** (Chrome, Firefox, Edge…)
- [ ] Un **account GitHub** gratuito - [registrati qui](https://github.com/signup)
- [ ] Un **account Playit.gg** gratuito - [registrati qui](https://playit.gg)

**Nessun software da installare sul tuo computer.**

---

## 📂 File del repository (In arrivo)

⚠️ Questa sezione è in fase di costruzione.  
Le informazioni che seguono sono solo indicative.  
Vedi la guida nella cartella [`Docs`](Docs).

| File | Ruolo |
|---|---|
| `README.md` | Questo file - panoramica del progetto |
| `GUIDE.md` | 📘 **La guida completa**, passo dopo passo |
| `start.sh` | Avvia il server con le ottimizzazioni Aikar’s Flags |
| `keep-alive.sh` | Impedisce al Codespace di sospendersi automaticamente |
| `backup.sh` | Backup automatico del mondo Minecraft |

---

## 🚀 Avvio rapido (In arrivo)

⚠️ Questa sezione è in fase di costruzione.  
Le informazioni che seguono sono solo indicative.  
Vedi la guida nella cartella [`Docs`](Docs).

    # 1. Clona questo repository in un Codespace GitHub
    # 2. Installa Java 21
    sudo apt-get install -y openjdk-21-jdk

    # 3. Avvia il server
    bash start.sh

    # 4. Avvia il tunnel Playit.gg (in un secondo terminale)
    ./playit

    # 5. Apri Crafty Controller sulla porta 8443

> **Per la guida dettagliata, vedi [`IT_GUIDE.md`](Docs/IT_Guide.md).**

---

## 🗂️ Contenuto della guida

Il file `IT_GUIDE.md` copre i seguenti 17 passaggi:

1. Introduzione e requisiti hardware
2. Capire gli strumenti (Codespaces, PaperMC, Crafty, Playit.gg)
3. Creazione degli account GitHub e Playit.gg
4. Creazione del repository e del Codespace
5. Prendere confidenza con il terminale Linux
6. Installazione di Java 21
7. Installazione di Python 3 e pip
8. Download e configurazione di PaperMC
9. Configurazione di Playit.gg
10. Installazione di Crafty Controller
11. Aggiunta del server a Crafty
12. Script anti‑sospensione (keep‑alive)
13. Backup automatici
14. ✅ Checklist di avvio sessione
15. 🛑 Checklist di arresto sessione
16. Risoluzione dei problemi e supporto
17. Monitoraggio del consumo mensile

Ogni passaggio include: la spiegazione del *perché*, i comandi esatti da copiare e una verifica per assicurarsi che tutto funzioni.

---

## ⚠️ Limiti e uso responsabile

### Quota gratuita GitHub Codespaces

    120 core‑ore / mese  →  60 ore di gioco su una macchina a 2 core

| Cosa fare | Cosa evitare |
|---|---|
| ✅ Arrestare il Codespace dopo ogni sessione | ❌ Lasciarlo attivo 24 ore su 24 |
| ✅ Controllare Settings › Billing & plans | ❌ Ignorare il proprio consumo |
| ✅ Utilizzare per sessioni occasionali | ❌ Uso continuativo in produzione |

> ⚠️ Mantenere un server di gioco sempre attivo **non è conforme** ai termini di utilizzo di GitHub Codespaces. Questa guida è pensata per un uso saltuario e responsabile.

### Storage
- **32 GB** disponibili sulla macchina a 2 core
- I dati **non versionati** vengono persi se il Codespace viene eliminato
- Usa `backup.sh` ed esegui regolarmente il commit dei backup

---

## 🤝 Contribuire

Questa guida è mantenuta con cura, ma gli errori capitano. Hai trovato un refuso, un comando obsoleto o qualcosa da migliorare?

1. **Apri una [Issue](../../issues)** per segnalare il problema
2. **Invia una [Pull Request](../../pulls)** con le tue correzioni

---

## 💬 Supporto e community

| Risorsa | Per |
|---|---|
| [Discord PaperMC](https://discord.gg/papermc) | Domande sul server Minecraft |
| [Discord Playit.gg](https://discord.gg/playit) | Problemi di tunnel / rete |
| [Stack Overflow](https://stackoverflow.com) | Errori Linux / Java con tag `[minecraft]` `[github-codespaces]` |
| [Issues GitHub](../../issues) | Problemi specifici di questa guida |

---

## 📄 Licenza

Distribuito sotto licenza **MIT**. Libero di usare, modificare e ridistribuire mantenendo l’avviso di copyright.

---

<div align="center">

**Pronto a giocare?**

### 👉 [Apri la guida completa - IT_Guide.md](Tutorial/🇮🇹It_Guide.md)

*Grazie alle community PaperMC, Crafty Controller, Playit.gg e GitHub.*

</div>
