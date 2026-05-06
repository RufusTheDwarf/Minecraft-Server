# 🟩 Serveur Minecraft gratuit sur GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-éducatif%20%2F%20privé-lightgrey?style=flat-square)

> ⚠️ Ce guide est prévu pour un usage éducatif et privé. Faire tourner un serveur 24h/24 dans Codespaces n'est pas conforme aux CGU de GitHub. Le script anti-veille sert uniquement à éviter les coupures *pendant* une session de jeu, dans le respect du quota de 60 h/mois.

---

## 📋 Table des matières

- [Ce qu'on va faire](#-ce-quon-va-faire)
- [Ce qu'il vous faut](#-ce-quil-vous-faut)
- [Étape 0 — Comprendre les outils](#-étape-0--comprendre-les-outils)
- [Étape 1 — Créer les comptes](#-étape-1--créer-les-comptes)
- [Étape 2 — Créer le dépôt et le Codespace](#-étape-2--créer-le-dépôt-et-le-codespace)
- [Étape 3 — Se repérer dans le terminal](#-étape-3--se-repérer-dans-le-terminal)
- [Étape 4 — Installer Java 21](#-étape-4--installer-java-21-lts)
- [Étape 5 — Installer Python 3 et pip](#-étape-5--installer-python-3-et-pip)
- [Étape 6 — Télécharger PaperMC](#-étape-6--télécharger-et-préparer-papermc)
- [Étape 7 — Configurer Playit.gg](#-étape-7--configurer-playitgg)
- [Étape 8 — Installer Crafty Controller](#-étape-8--installer-crafty-controller)
- [Étape 9 — Ajouter le serveur dans Crafty](#-étape-9--ajouter-le-serveur-dans-crafty)
- [Étape 10 — Script anti-veille](#-étape-10--script-anti-veille)
- [Étape 11 — Sauvegardes automatiques](#-étape-11--sauvegardes-automatiques)
- [🟢 Démarrer une session](#-démarrer-une-session)
- [🔴 Arrêter une session](#-arrêter-une-session)
- [Dépannage](#-dépannage)
- [Surveiller son quota](#-surveiller-son-quota)

---

## 🎯 Ce qu'on va faire

Utiliser le crédit gratuit de GitHub Codespaces pour faire tourner un serveur Minecraft dans le cloud, le gérer via une interface web (Crafty Controller), et le rendre accessible à vos amis depuis Internet sans toucher à votre box — grâce à Playit.gg.

Aucune connaissance préalable requise. Chaque commande est expliquée.

---

## 🧰 Ce qu'il vous faut

Tout est gratuit.

| | Élément | Détail |
|---|---|---|
| 🌐 | Un navigateur web | Chrome, Firefox, Edge — version récente |
| 📧 | Une adresse e-mail | Pour créer les deux comptes |
| 🐙 | Un compte GitHub | Créé à l'étape 1 |
| 🎮 | Un compte Playit.gg | Créé à l'étape 1 |
| ⏱️ | ~45 minutes | Pour la première installation |

> 💡 Une fois en place, relancer le serveur pour une nouvelle session prend moins de 3 minutes.

---

## 🔍 Étape 0 — Comprendre les outils

Cinq minutes à lire maintenant vous éviteront beaucoup de confusion par la suite.

| Outil | Rôle |
|---|---|
| **GitHub Codespaces** | Un ordinateur Linux dans le cloud, accessible depuis le navigateur. L'offre gratuite donne **120 core-hours/mois** → avec la machine 2 cœurs, ça fait **60 heures de jeu réelles**. |
| **PaperMC** | Le moteur du serveur. Version améliorée du logiciel officiel Mojang : plus fluide, moins de lag, compatible plugins. |
| **Playit.gg** | Le tunnel. GitHub ne donne pas d'IP publique — Playit.gg en crée une (`monserveur.playit.gg`) que vos amis entrent directement dans Minecraft. |
| **Crafty Controller** | Le panneau de contrôle web. Démarrer, arrêter, surveiller le serveur en cliquant sur des boutons. |

---

## 👤 Étape 1 — Créer les comptes

### 🐙 GitHub

1. Allez sur [github.com/signup](https://github.com/signup)
2. Entrez un e-mail, un mot de passe et un nom d'utilisateur
3. Résolvez le puzzle → **Create account**
4. Récupérez le code à 6 chiffres dans votre boîte mail et saisissez-le

✅ Vous voyez votre nom d'utilisateur en haut à droite du tableau de bord GitHub.

### 🎮 Playit.gg

1. Allez sur [playit.gg](https://playit.gg)
2. **Login** → en bas du formulaire → **Sign up**
3. Remplissez les champs et validez
4. Cliquez sur le lien de confirmation reçu par mail

✅ Vous pouvez accéder à votre tableau de bord Playit.gg.

---

## 🏗️ Étape 2 — Créer le dépôt et le Codespace

### Le dépôt

Un dépôt (*repository*) est un dossier de projet sur GitHub. Il sert de base pour créer le Codespace.

1. Sur GitHub : **`+`** en haut à droite → **New repository**
2. Remplissez :
   - **Repository name :** `mc-server`
   - **Visibility :** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ Vous êtes sur la page de votre dépôt `mc-server`.

### Le Codespace

> ⚠️ **Étape critique** — le choix de la machine détermine votre quota. Se tromper ici le divise par deux.

1. Bouton vert **`<> Code`** → onglet **Codespaces**
2. **`...`** (à droite de "Create codespace on main") → **New with options**
3. **Machine type** → **`2-core`** (8 Go RAM) — ne pas choisir 4-core
4. **Create codespace** → patientez 2-3 minutes

Un éditeur VS Code s'ouvre dans votre navigateur avec un terminal en bas.

✅ Vous voyez l'invite de commande dans le terminal.

---

## 💻 Étape 3 — Se repérer dans le terminal

Le terminal est la zone où vous tapez des commandes. Copiez-collez simplement ce que le guide indique.

| Commande | Ce qu'elle fait |
|---|---|
| `cd ~` | Retourner au dossier personnel |
| `cd ~/minecraft-server` | Aller dans le dossier du serveur |
| `pwd` | Afficher où vous êtes |
| `mkdir -p nom` | Créer un dossier |
| `ls` | Lister les fichiers |
| `sudo` | Exécuter en administrateur |

> 💡 **Règle d'or :** chaque étape de ce guide précise le dossier depuis lequel lancer la commande. En cas de doute, tapez `pwd`.

---

## ☕ Étape 4 — Installer Java 21 (LTS)

Minecraft est écrit en Java. La version **21** est celle recommandée par PaperMC — c'est la version **LTS** (Long-Term Support) : la plus stable, la plus longtemps maintenue. Des versions plus récentes existent mais ne sont pas LTS.

📍 *Depuis n'importe quel dossier.*

Vérifiez d'abord si Java est déjà là :

```bash
java -version
```

🔵 Si vous voyez `openjdk version "21.0.x"` → passez à l'étape 5.

Sinon :

```bash
sudo apt update -y
sudo apt install openjdk-21-jre-headless -y
```

```bash
java -version
```

✅ La commande affiche `openjdk version "21.0.x"`.

---

## 🐍 Étape 5 — Installer Python 3 et pip

Crafty Controller est développé en Python. On a besoin de Python 3 et de `pip` (son gestionnaire de modules) pour l'installer et le faire tourner.

📍 *Depuis votre dossier personnel (`cd ~`).*

```bash
sudo apt install python3 python3-pip -y
```

```bash
python3 --version && pip3 --version
```

✅ Les deux commandes affichent un numéro de version, sans erreur.

---

## 🧱 Étape 6 — Télécharger et préparer PaperMC

### Créer le dossier

📍 *Depuis votre dossier personnel (`cd ~`).*

```bash
mkdir -p ~/minecraft-server
cd ~/minecraft-server
```

### Installer jq

`jq` lit les réponses de l'API PaperMC pour récupérer automatiquement le dernier build stable.

```bash
sudo apt install jq -y
```

### Télécharger PaperMC

```bash
wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar
```

> 🔵 Si la commande échoue, utilisez ce build fixe :
> ```bash
> wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar
> ```

✅ `ls` affiche `server.jar` dans la liste.

### Accepter l'EULA

> ⚠️ **Obligation légale.** Mojang exige l'acceptation du contrat de licence (EULA) avant tout démarrage. Sans ce fichier, le serveur refuse de se lancer. En exécutant la commande ci-dessous, vous acceptez les termes sur [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

```bash
echo "eula=true" > eula.txt
```

✅ `ls` montre `eula.txt` à côté de `server.jar`.

### Premier lancement de test

```bash
java -Xms2G -Xmx4G -jar server.jar --nogui
```

Attendez le message `Done!` (1-2 min), puis arrêtez :

```bash
stop
```

✅ Le serveur s'arrête proprement et vous retrouvez l'invite de commande.

### Créer le script de démarrage

Ces paramètres s'appellent les *Aikar's flags* — des optimisations mémoire reconnues dans la communauté Minecraft pour réduire significativement les lags.

📍 *Retournez dans votre dossier personnel (`cd ~`).*

```bash
nano start.sh
```

Collez :

```bash
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
```

Sauvegardez : **Ctrl+X** → **Y** → **Entrée**

```bash
chmod +x ~/start.sh
```

✅ `ls -l ~/start.sh` affiche `-rwxr-xr-x` en début de ligne.

---

## 📡 Étape 7 — Configurer Playit.gg

Votre Codespace n'a pas d'adresse IP publique. Playit.gg crée un tunnel et vous fournit une adresse que vos amis entrent directement dans Minecraft — aucune configuration réseau de votre côté.

📍 *Depuis votre dossier personnel (`cd ~`).*

### Installer l'agent

```bash
curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash
```

### Lier l'agent à votre compte

```bash
playit
```

Un lien d'authentification apparaît dans le terminal. Ouvrez-le dans votre navigateur → connectez-vous → **Claim Agent**. Revenez dans le terminal → **Ctrl+C** → relancez en arrière-plan :

```bash
playit &
```

### Créer le tunnel

1. Sur [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Remplissez :
   - **Type :** `Minecraft Java (Game)`
   - **Name :** `MonServeur`
   - **Local Port :** `25565`
3. **Add Tunnel**

📌 L'adresse publique s'affiche (ex. `monserveur.playit.gg:12345`). **Notez-la — c'est ce que vous donnez à vos amis.**

✅ Le tunnel apparaît dans le tableau de bord avec le statut "Connected".

---

## 🎛️ Étape 8 — Installer Crafty Controller

Crafty Controller est un panneau de contrôle web : démarrer, arrêter, voir les logs, gérer les joueurs — depuis l'interface, sans ligne de commande.

📍 *Depuis votre dossier personnel (`cd ~`).*

```bash
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
cd crafty-installer-4.0
sudo ./install_crafty.sh
```

Le script pose quelques questions :

| Question | Réponse |
|---|---|
| Port | Appuyez sur **Entrée** (garde `8443`) |
| Utilisateur | `crafty` |
| Mot de passe admin | Choisissez-en un et **notez-le** |
| Confirmation | `y` |

L'installation prend 3-5 minutes.

### Démarrer Crafty

```bash
sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"
```

### Rendre l'interface accessible

1. VS Code → onglet **PORTS** en bas
2. Si `8443` n'apparaît pas → **Add Port** → `8443` → validez
3. Clic droit sur `8443` → **Port Visibility** → **Public**
4. Ouvrez l'URL générée dans un nouvel onglet
5. Avertissement de sécurité → **Avancé** → **Procéder**
6. Connectez-vous : `admin` + votre mot de passe

✅ Vous êtes sur le tableau de bord Crafty Controller.

---

## 🔗 Étape 9 — Ajouter le serveur dans Crafty

**Servers** → **Create Server** → remplissez :

| Champ | Valeur |
|---|---|
| Server Name | `MonServeur` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 Au tout premier démarrage, Crafty peut afficher un pop-up pour accepter l'EULA. Cliquez sur **I Accept** puis relancez.

✅ Le serveur passe en statut "Running" (vert) dans l'interface.

---

## ⏳ Étape 10 — Script anti-veille

Un Codespace s'arrête automatiquement après 30 minutes d'inactivité. Ce script envoie un signal toutes les 10 minutes pour maintenir la session active pendant vos parties.

📍 *Depuis votre dossier personnel (`cd ~`).*

```bash
nano keep-alive.sh
```

Collez :

```bash
#!/bin/bash
# Maintien d'activité pour GitHub Codespaces
while true; do
    echo "$(date) - keep-alive ping" >> ~/keep-alive.log
    sleep 600
done
```

**Ctrl+X** → **Y** → **Entrée**, puis :

```bash
chmod +x ~/keep-alive.sh
nohup ~/keep-alive.sh &
```

`nohup` empêche le script de s'arrêter si votre session se ferme. Le `&` le passe en tâche de fond.

✅ Après quelques minutes, `cat ~/keep-alive.log` affiche des lignes horodatées.

---

## 💾 Étape 11 — Sauvegardes automatiques

Ce script crée une archive compressée de votre monde toutes les heures. En cas de corruption, vous revenez à une sauvegarde récente.

📍 *Depuis votre dossier personnel (`cd ~`).*

```bash
mkdir -p ~/minecraft-server-backups
nano backup.sh
```

Collez :

```bash
#!/bin/bash
# Sauvegarde automatique du monde Minecraft
tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
  -C ~/minecraft-server world world_nether world_the_end
echo "$(date) - Sauvegarde effectuée." >> ~/backup.log
```

**Ctrl+X** → **Y** → **Entrée**, puis :

```bash
chmod +x ~/backup.sh
(crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -
```

✅ `crontab -l` affiche la ligne de planification.

---

## 🟢 Démarrer une session

> 📌 À chaque ouverture du Codespace, copiez-collez ces 4 commandes dans le terminal dans cet ordre.

```bash
# 1. Anti-veille
nohup ~/keep-alive.sh &

# 2. Tunnel Playit.gg
playit &

# 3. Serveur Minecraft
cd ~/minecraft-server && ~/start.sh &

# 4. Interface Crafty
sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &
```

Attendez 1-2 minutes → vérifiez "Running" dans Crafty → donnez l'adresse Playit.gg à vos amis. 🎮

---

## 🔴 Arrêter une session

> ⚠️ **Fermer l'onglet ne suffit pas.** Le Codespace continue de tourner en arrière-plan et consomme votre quota. Suivez ces étapes à chaque fin de session.

**1 — Arrêter le serveur Minecraft**

Via Crafty : bouton ⏹️ dans l'interface.

Via le terminal :
```bash
kill $(pgrep -f "server.jar")
```

**2 — Arrêter les processus en arrière-plan**

```bash
pkill -f playit
pkill -f keep-alive.sh
pkill -f "python3 main.py"
```

**3 — Arrêter le Codespace** ← étape la plus importante

Depuis GitHub (recommandé) :
1. [github.com/codespaces](https://github.com/codespaces)
2. Votre Codespace actif (🟢 point vert)
3. **`...`** → **Stop codespace**

Depuis l'éditeur : bas à gauche → nom du Codespace → **Stop Current Codespace**

✅ Le point vert devient gris. Le Codespace est arrêté.

---

## 🆘 Dépannage

| Symptôme | Solution |
|---|---|
| ❌ `java -version` n'affiche pas `21.x` | Refaites l'étape 4 depuis le début |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` sur un `.sh` | `chmod +x nom_du_script.sh` |
| ❌ Serveur refuse de démarrer (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ L'adresse Playit.gg ne fonctionne pas | `ps aux \| grep playit` → si absent, relancez : `playit &` |
| ❌ Crafty inaccessible (port 8443) | Onglet **PORTS** → clic droit `8443` → **Port Visibility** → **Public** |
| ❌ Codespace s'arrête en pleine partie | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` puis relancez le téléchargement |
| ❌ `OutOfMemoryError` dans les logs | Vérifiez que la machine est bien **2-core / 8 Go RAM** |

Pour tout autre problème : copiez le message d'erreur exact sur [Stack Overflow](https://stackoverflow.com) avec le tag `[minecraft]` ou `[github-codespaces]`. Communautés : [Discord PaperMC](https://discord.gg/papermc) · [Discord Playit.gg](https://discord.gg/playit-gg)

---

## 📊 Surveiller son quota

GitHub offre **120 core-hours gratuits par mois**. Avec la machine 2 cœurs, chaque heure de jeu en consomme 2 → **60 heures réelles par mois**.

Pour voir votre consommation : **avatar GitHub** → **Settings** → **Billing & plans** → **Usage this month** → ligne **Codespaces**

> ⚠️ Si vous approchez des 120 core-hours, arrêtez le Codespace immédiatement et attendez le renouvellement mensuel.

---

## 📎 Ressources

- [Documentation PaperMC](https://docs.papermc.io)
- [Documentation Crafty Controller](https://docs.craftycontrol.com)
- [Documentation Playit.gg](https://playit.gg/support)
- [Documentation GitHub Codespaces](https://docs.github.com/en/codespaces)
- [Discord PaperMC](https://discord.gg/papermc)
- [Discord Playit.gg](https://discord.gg/playit-gg)

---

*Testé sur un Codespace fraîchement créé — mai 2026.*
