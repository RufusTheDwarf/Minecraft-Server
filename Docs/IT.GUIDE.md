# 🟩 Server Minecraft Gratuito su GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ Questa guida è destinata a uso educativo e privato. Mantenere un server 24/7 su Codespaces non è conforme ai Termini di Servizio di GitHub. Lo script anti-sospensione serve solo a evitare disconnessioni *durante* una sessione di gioco, entro la quota di 60 ore/mese. O un certo Git busserà alla tua porta alle 3 del mattino...

---

## 📋 Indice

- [Cosa faremo](#-cosa-faremo)
- [Cosa ti serve](#-cosa-ti-serve)
- [Passo 0 - Capire gli strumenti](#-passo-0--capire-gli-strumenti)
- [Passo 1 - Creare gli account](#-passo-1--creare-gli-account)
- [Passo 2 - Creare il repository e il Codespace](#-passo-2--creare-il-repository-e-il-codespace)
- [Passo 3 - Orientarsi nel terminale](#-passo-3--orientarsi-nel-terminale)
- [Passo 4 - Installare Java 21 LTS](#-passo-4--installare-java-21-lts)
- [Passo 5 - Installare Python 3 e pip](#-passo-5--installare-python-3-e-pip)
- [Passo 6 - Scaricare e preparare PaperMC](#-passo-6--scaricare-e-preparare-papermc)
- [Passo 7 - Configurare Playit.gg](#-passo-7--configurare-playitgg)
- [Passo 8 - Installare Crafty Controller](#-passo-8--installare-crafty-controller)
- [Passo 9 - Aggiungere il server a Crafty](#-passo-9--aggiungere-il-server-a-crafty)
- [Passo 10 - Script anti-sospensione](#-passo-10--script-anti-sospensione)
- [Passo 11 - Backup automatici](#-passo-11--backup-automatici)
- [🟢 Avviare una sessione](#-avviare-una-sessione)
- [🔴 Arrestare una sessione](#-arrestare-una-sessione)
- [Risoluzione dei problemi](#-risoluzione-dei-problemi)
- [Monitorare la tua quota](#-monitorare-la-tua-quota)

---

## 🎯 Cosa faremo

Usare i crediti gratuiti di GitHub Codespaces per eseguire un server Minecraft nel cloud, gestirlo tramite un'interfaccia web (Crafty Controller) e renderlo accessibile ai tuoi amici su Internet senza toccare il router, grazie a Playit.gg.

Nessuna conoscenza preliminare richiesta. Ogni comando è spiegato.

---

## 🧰 Cosa ti serve

Tutto è gratuito.

| | Elemento | Dettaglio |
|---|---|---|
| 🌐 | Un browser web | Chrome, Firefox, Edge |
| 📧 | Un indirizzo email | Per creare i due account |
| 🐙 | Un account GitHub | Creato al Passo 1 |
| 🎮 | Un account Playit.gg | Creato al Passo 1 |
| ⏱️ | ~45 minuti | Per la prima installazione |

> 💡 Una volta configurato, riavviare il server per una nuova sessione richiede meno di 3 minuti.

---

## 🔍 Passo 0  Capire gli strumenti

Cinque minuti di lettura ora ti eviteranno molta confusione dopo.

| Strumento | Ruolo |
|---|---|
| **GitHub Codespaces** | Un computer Linux nel cloud, accessibile dal browser. Il piano gratuito offre **120 core-ore/mese** → con la macchina a 2 core, sono **60 ore di gioco effettive**. |
| **PaperMC** | Il motore del server. Versione migliorata del software ufficiale Mojang: più fluida, meno lag, compatibile con plugin. |
| **Playit.gg** | Il tunnel. GitHub non fornisce un IP pubblico. Playit.gg ne crea uno (`mioserver.playit.gg`) che gli amici inseriscono direttamente su Minecraft. |
| **Crafty Controller** | Il pannello di controllo web. Avviare, fermare, monitorare il server con un clic. |

---

## 👤 Passo 1  Creare gli account

### 🐙 GitHub

1. Vai su [github.com/signup](https://github.com/signup)
2. Inserisci un'email, una password e un nome utente
3. Risolvi il puzzle → **Create account**
4. Recupera il codice a 6 cifre dalla tua casella email e inseriscilo

✅ Vedi il tuo nome utente in alto a destra nella dashboard di GitHub.

### 🎮 Playit.gg

1. Vai su [playit.gg](https://playit.gg)
2. **Login** → in fondo al modulo → **Sign up**
3. Compila i campi e conferma
4. Clicca sul link di conferma ricevuto via email

✅ Puoi accedere alla dashboard di Playit.gg.

---

## 🏗️ Passo 2  Creare il repository e il Codespace

### Il repository

Un repository è una cartella di progetto su GitHub. Serve come base per creare il Codespace.

1. Su GitHub: **`+`** in alto a destra → **New repository**
2. Compila:
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ Sei sulla pagina del tuo repository `mc-server`.

### Il Codespace

> ⚠️ **Passo critico** - la scelta della macchina determina la quota. Sbagliare qui la dimezza.

1. **`Menu`** → scheda **Codespaces**
2. In alto a destra clicca **New Codespace**
3. Scegli il repository che hai creato per il server Minecraft
4. Scegli la regione più vicina a te (riduce il ping tra te e il server)
5. **Machine type** → **`2-core`** (8 GB RAM) - non scegliere 4-core
6. **Create codespace** → attendi 2-3 minuti

Si apre un editor VS Code nel browser con un terminale in basso.

✅ Vedi il prompt dei comandi nel terminale.

---

## 💻 Passo 3  Orientarsi nel terminale

Il terminale è dove digiti i comandi. Copia e incolla semplicemente ciò che indica la guida.

| Comando | Cosa fa |
|---|---|
| `cd ~` | Torna alla cartella home |
| `cd ~/minecraft-server` | Va nella cartella del server |
| `pwd` | Mostra dove ti trovi |
| `mkdir -p nome` | Crea una cartella |
| `ls` | Elenca i file |
| `sudo` | Esegue come amministratore |

> 💡 **Regola d'oro:** ogni passo di questa guida specifica da quale cartella eseguire il comando. In caso di dubbio, digita `pwd`.

---

## ☕ Passo 4  Installare Java 21 (LTS)

Minecraft è scritto in Java. La versione **21** è quella consigliata da PaperMC. È la versione **LTS** (Long-Term Support): la più stabile e con manutenzione più lunga. Esistono versioni più recenti ma non sono LTS.

📍 *Da qualsiasi cartella.*

Per prima cosa, verifica se Java è già presente:

    java -version

🔵 Se vedi `openjdk version "21.0.x"` → passa al Passo 5.

Altrimenti:

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ Il comando mostra `openjdk version "21.0.x"`.

---

## 🐍 Passo 5  Installare Python 3 e pip

Crafty Controller è sviluppato in Python. Ci servono Python 3 e `pip` (il suo gestore di pacchetti) per installarlo ed eseguirlo.

📍 *Dalla tua cartella home (`cd ~`).*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ Entrambi i comandi mostrano un numero di versione senza errori.

---

## 🧱 Passo 6  Scaricare e preparare PaperMC

### Creare la cartella

📍 *Dalla tua cartella home (`cd ~`).*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### Installare jq

`jq` legge le risposte dell'API di PaperMC per recuperare automaticamente l'ultima build stabile.

    sudo apt install jq -y

### Scaricare PaperMC

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 Se il comando fallisce, usa questa build fissa:
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` mostra `server.jar` nell'elenco.

### Accettare l'EULA

> ⚠️ **Obbligo legale.** Mojang richiede l'accettazione del Contratto di Licenza con l'Utente Finale (EULA) prima di ogni avvio. Senza questo file, il server si rifiuta di partire. Eseguendo il comando qui sotto, accetti i termini su [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

    echo "eula=true" > eula.txt

✅ `ls` mostra `eula.txt` accanto a `server.jar`.

### Primo avvio di test

    java -Xms2G -Xmx4G -jar server.jar --nogui

Attendi il messaggio `Done!` (1-2 min), poi ferma:

    stop

✅ Il server si arresta correttamente e recuperi il prompt.

### Creare lo script di avvio

Questi parametri sono chiamati *Aikar's flags*. Ottimizzazioni della memoria riconosciute dalla community che riducono significativamente i lag.

📍 *Torna alla tua cartella home (`cd ~`).*

    nano start.sh

Incolla:

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

Salva: **Ctrl+X** → **Y** → **Invio**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` mostra `-rwxr-xr-x` all'inizio della riga.

---

## 📡 Passo 7  Configurare Playit.gg

Il tuo Codespace non ha un IP pubblico. Playit.gg crea un tunnel e fornisce un indirizzo che gli amici inseriscono direttamente in Minecraft. Nessuna configurazione di rete da parte tua.

📍 *Dalla tua cartella home (`cd ~`).*

### Installare l'agente

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### Collegare l'agente al tuo account

    playit

Nel terminale appare un link di autenticazione. Aprilo nel browser → accedi → **Claim Agent**. Torna al terminale → **Ctrl+C** → riesegui in background:

    playit &

### Creare il tunnel

1. Su [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Compila:
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MioServer`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 Viene visualizzato l'indirizzo pubblico (es. `mioserver.playit.gg:12345`). **Prendi nota. È questo che darai ai tuoi amici.**

✅ Il tunnel appare nella dashboard con lo stato "Connected".

---

## 🎛️ Passo 8  Installare Crafty Controller

Crafty Controller è un pannello di controllo web: avvia, ferma, visualizza i log, gestisci i giocatori da interfaccia, senza riga di comando.

📍 *Dalla tua cartella home (`cd ~`).*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

Lo script fa alcune domande:

| Domanda | Risposta |
|---|---|
| Porta | Premi **Invio** (mantiene `8443`) |
| Utente | `crafty` |
| Password admin | Scegline una e **prendi nota** |
| Conferma | `y` |

L'installazione richiede 3-5 minuti.

### Avviare Crafty

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### Rendere accessibile l'interfaccia

1. VS Code → scheda **PORTS** in basso
2. Se `8443` non compare → **Add Port** → `8443` → conferma
3. Clic destro su `8443` → **Port Visibility** → **Public**
4. Apri l'URL generato in una nuova scheda
5. Avviso di sicurezza → **Avanzate** → **Procedi**
6. Accedi: `admin` + la tua password

✅ Sei sulla dashboard di Crafty Controller.

---

## 🔗 Passo 9  Aggiungere il server a Crafty

**Servers** → **Create Server** → compila:

| Campo | Valore |
|---|---|
| Server Name | `MioServer` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 Al primissimo avvio, Crafty potrebbe mostrare un pop-up per accettare l'EULA. Clicca su **I Accept** e poi riavvia.

✅ Il server passa allo stato "Running" (verde) nell'interfaccia.

---

## ⏳ Passo 10  Script anti-sospensione

Un Codespace si ferma automaticamente dopo 30 minuti di inattività. Questo script invia un segnale ogni 10 minuti per mantenere attiva la sessione durante le tue partite.

📍 *Dalla tua cartella home (`cd ~`).*

    nano keep-alive.sh

Incolla:

    #!/bin/bash
    # Keep-alive per GitHub Codespaces
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Invio**, poi:

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` impedisce che lo script si fermi se la sessione si chiude. `&` lo esegue in background.

✅ Dopo qualche minuto, `cat ~/keep-alive.log` mostra righe con data e ora.

---

## 💾 Passo 11  Backup automatici

Questo script crea un archivio compresso del tuo mondo ogni ora. In caso di corruzione, puoi ripristinare un backup recente.

📍 *Dalla tua cartella home (`cd ~`).*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

Incolla:

    #!/bin/bash
    # Backup automatico del mondo Minecraft
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - Backup completato." >> ~/backup.log

**Ctrl+X** → **Y** → **Invio**, poi:

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` mostra la riga pianificata.

---

## 🟢 Avviare una sessione

> 📌 Ogni volta che apri il Codespace, copia e incolla questi 4 comandi nel terminale, in quest'ordine.

    # 1. Anti-sospensione
    nohup ~/keep-alive.sh &

    # 2. Tunnel Playit.gg
    playit &

    # 3. Server Minecraft
    cd ~/minecraft-server && ~/start.sh &

    # 4. Interfaccia Crafty
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

Attendi 1-2 minuti → verifica "Running" in Crafty → dai l'indirizzo Playit.gg ai tuoi amici. 🎮

---

## 🔴 Arrestare una sessione

> ⚠️ **Chiudere la scheda non basta.** Il Codespace continua a funzionare in background e consuma la tua quota. Segui questi passi alla fine di ogni sessione.

**1. Fermare il server Minecraft**

Via Crafty: clicca il pulsante ⏹️ nell'interfaccia.

Via terminale:

    kill $(pgrep -f "server.jar")

**2. Fermare i processi in background**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Arrestare il Codespace** ← passo più importante

Da GitHub (consigliato):
1. [github.com/codespaces](https://github.com/codespaces)
2. Il tuo Codespace attivo (🟢 punto verde)
3. **`...`** → **Stop codespace**

Dall'editor: in basso a sinistra → nome del Codespace → **Stop Current Codespace**

✅ Il punto verde diventa grigio. Il Codespace è fermo.

---

## 🆘 Risoluzione dei problemi

| Sintomo | Soluzione |
|---|---|
| ❌ `java -version` non mostra `21.x` | Rifai il Passo 4 dall'inizio |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` su un `.sh` | `chmod +x nome_script.sh` |
| ❌ Il server non si avvia (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ L'indirizzo Playit.gg non funziona | `ps aux \| grep playit` → se assente, rilancia: `playit &` |
| ❌ Crafty non raggiungibile (porta 8443) | Scheda **PORTS** → clic destro `8443` → **Port Visibility** → **Public** |
| ❌ Il Codespace si ferma durante la partita | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` poi riprova il download |
| ❌ `OutOfMemoryError` nei log | Verifica che la macchina sia **2-core / 8 GB RAM** |

Per qualsiasi altro problema: copia il messaggio di errore esatto su [Stack Overflow](https://stackoverflow.com) con il tag `[minecraft]` o `[github-codespaces]`. Community: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 Monitorare la tua quota

GitHub offre **120 core-ore gratuite al mese**. Con la macchina a 2 core, ogni ora di gioco consuma 2 → **60 ore effettive al mese**.

Per vedere il tuo consumo: **avatar GitHub** → **Settings** → **Billing & plans** → **Usage this month** → riga **Codespaces**

> ⚠️ Se ti stai avvicinando a 120 core-ore, ferma immediatamente il Codespace e attendi il rinnovo mensile.

---

## 📎 Risorse

- [Documentazione PaperMC](https://docs.papermc.io)
- [Documentazione Crafty Controller](https://docs.craftycontrol.com)
- [Documentazione Playit.gg](https://playit.gg/support)
- [Documentazione GitHub Codespaces](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*Testato su un Codespace appena creato - maggio 2026.*
