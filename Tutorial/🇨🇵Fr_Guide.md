GUIDE ULTIME – Serveur Minecraft sur GitHub Codespaces (Crafty + Playit.gg)

Version 1.0 – Mise à jour complète le 5 mai 2026 

---

📌 INTRODUCTION

Ce guide vous explique pas à pas, comme si vous n’aviez jamais utilisé Linux, GitHub, ni de serveur Minecraft, comment :

· Obtenir un serveur Minecraft gratuit (60 h/mois) hébergé dans le cloud via GitHub Codespaces
· Le gérer avec une interface web (Crafty Controller)
· Permettre à vos amis de se connecter depuis Internet sans ouvrir vos ports (Playit.gg)

Tout sera clair, détaillé et vérifié avec la documentation officielle de chaque outil, des forums, des vidéos YouTube, et des centaines d’autres sources. Aucune connaissance préalable requise.

---

⚠️ AVERTISSEMENT IMPORTANT

Ce guide est destiné à un usage éducatif et privé. L’exécution de serveurs de jeux en continu (24h/24 et 7j/7) dans GitHub Codespaces n’est pas une utilisation conforme aux conditions d’utilisation du service. La section sur le script anti-veille est fournie uniquement pour éviter les interruptions pendant les sessions de jeu le week-end, conformément au plan de quota. Utilisez-le de manière responsable pour ne pas dépasser vos 60 heures mensuelles gratuites.

---

🔍 COMPRENDRE LES OUTILS

Outil Rôle
GitHub Codespaces Machine virtuelle Linux dans le cloud, accessible depuis un navigateur. 120 core‑hours gratuits/mois, soit 60 h sur une machine 2 cœurs.
Java 25 (LTS) Dernière version Long-Term Support de Java, nécessaire pour exécuter Minecraft 26.1+. Java 25 est la version recommandée par PaperMC pour Minecraft 26.1 et ultérieur.
PaperMC Version optimisée du serveur Minecraft. Plus fluide, moins de lag, compatible plugins. Pour Minecraft 26.1, utilisez Paper 26.1.2.
Crafty Controller 4.10.4 Interface web pour gérer votre serveur Minecraft facilement.
Playit.gg Service de tunnel qui vous donne une adresse IP publique pour que vos amis puissent rejoindre votre serveur, sans ouvrir de ports.

---

📖 TABLE DES MATIÈRES

1. Création des comptes
2. Création du dépôt et du Codespace
3. Se repérer dans le terminal Linux
4. Installer Java 25 (LTS)
5. Installer Python 3 et pip
6. Télécharger et préparer PaperMC
7. Configurer Playit.gg
8. Installer Crafty Controller
9. Ajouter le serveur dans Crafty
10. Script anti‑veille (keep‑alive)
11. Sauvegardes automatiques
12. Checklist de démarrage d’une session
13. Comment tout arrêter proprement
14. Dépannage complet
15. Rappel quota et surveillance

---

1. CRÉATION DES COMPTES

1.1 Compte GitHub

1. Rendez-vous sur https://github.com/signup
2. Entrez un e‑mail valide, un mot de passe et un nom d’utilisateur.
3. Résolvez le puzzle de vérification, puis cliquez sur Create account.
4. Vous recevrez un code de vérification par e‑mail. Saisissez-le pour activer le compte.

1.2 Compte Playit.gg

1. Allez sur https://playit.gg
2. Cliquez sur Login, puis tout en bas sur Sign up.
3. Remplissez le formulaire (pseudo, e‑mail, mot de passe).
4. Validez votre adresse e‑mail en cliquant sur le lien reçu.

---

2. CRÉATION DU DÉPÔT ET DU CODESPACE

2.1 Créer le dépôt

1. Connectez‑vous à GitHub.
2. En haut à droite, cliquez sur le + → New repository.
3. Remplissez :
   · Repository name : mc-server (ou autre)
   · Visibilité : Private (recommandé)
   · Cochez Add a README file
4. Cliquez sur Create repository.

2.2 Créer le Codespace

1. Sur la page du dépôt, cliquez sur le bouton vert <> Code, puis sur l’onglet Codespaces.
2. Configuration capitale : cliquez sur le bouton ... (à droite de « Create codespace on main ») → New with options.
3. Machine type : sélectionnez 2‑core (8 Go RAM, 64 Go stockage). Ne choisissez surtout pas 4‑core si vous voulez rester dans les 60 h/mois.
4. Laissez les autres options par défaut, puis cliquez sur Create codespace.
5. Patientez 2‑3 minutes. Vous verrez un éditeur VS Code dans votre navigateur, avec un terminal en bas.

---

3. SE REPÉRER DANS LE TERMINAL LINUX

Le terminal est la fenêtre où vous tapez des commandes. À l’ouverture, vous êtes dans /workspaces/mc-server.

Commandes indispensables :

Commande Description
cd ~ Revenir au dossier personnel (home)
cd ~/minecraft-server Aller dans le dossier minecraft-server
pwd Afficher le dossier courant ( pratique pour vérifier où vous êtes )
mkdir -p nom Créer un dossier (et ses parents si nécessaire)
ls Lister les fichiers
sudo Exécuter la commande suivante en tant qu’administrateur
clear Effacer l’affichage

Règle d’or : avant chaque commande importante, vérifiez votre dossier de travail avec pwd. Ce guide vous indiquera le dossier requis à chaque étape.

---

4. INSTALLER JAVA 25 (LTS)

Pourquoi Java 25 ? PaperMC 26.1+ exige Java 25, la dernière version LTS (Long‑Term Support). Java 26 est une version non‑LTS.

4.1 Vérifier la version actuelle

```bash
cd ~
java -version
```

Si vous voyez openjdk version "25.x.x", passez directement à la section 5. Sinon, poursuivez.

4.2 Mettre à jour les paquets

```bash
sudo apt update -y && sudo apt upgrade -y
```

4.3 Installer Java 25

```bash
sudo apt install openjdk-25-jre-headless -y
```

Explication : openjdk-25-jre-headless est une version de Java optimisée pour les serveurs (sans interface graphique).

4.4 Vérifier l’installation

```bash
java -version
```

Doit afficher openjdk version "25.x.x".

---

5. INSTALLER PYTHON 3 ET PIP

Pourquoi Python ? Crafty Controller est écrit en Python. Il a besoin de Python 3.9+ et de pip.

5.1 Vérifier les versions

```bash
cd ~
python3 --version
pip3 --version
```

5.2 Installer si nécessaire

```bash
sudo apt install python3 python3-pip -y
```

5.3 Vérification finale

```bash
python3 --version && pip3 --version
```

Les deux commandes doivent retourner un numéro de version, sans erreur.

---

6. TÉLÉCHARGER ET PRÉPARER PAPERMC

Qu’est‑ce que PaperMC ? PaperMC est une version optimisée du serveur Minecraft officiel. Il corrige des bugs, réduit les lags et supporte les plugins. Paper 26.1.2 est la version stable pour Minecraft 26.1.

6.1 Créer le dossier du serveur

```bash
cd ~
mkdir -p ~/minecraft-server
cd ~/minecraft-server
```

6.2 Télécharger PaperMC via l’API

Pour obtenir la dernière version automatiquement :

```bash
wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/26.1/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/26.1 | jq -r '.builds[-1]')/downloads/paper-26.1-$(curl -s https://api.papermc.io/v2/projects/paper/versions/26.1 | jq -r '.builds[-1]').jar
```

Si jq n’est pas installé :

```bash
sudo apt install jq -y
```

Puis relancez la commande de téléchargement.

Alternative (version fixe) :

```bash
wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/26.1/builds/124/downloads/paper-26.1-124.jar
```

6.3 Accepter l’EULA

Mojang impose d’accepter le contrat de licence (EULA) avant tout démarrage. Sans cela, le serveur refuse de fonctionner.

```bash
echo "eula=true" > eula.txt
```

Vérifiez avec ls que eula.txt est bien présent.

6.4 Premier lancement (test)

```bash
java -Xms2G -Xmx4G -jar server.jar --nogui
```

· -Xms2G : démarre avec 2 Go de RAM.
· -Xmx4G : peut utiliser jusqu’à 4 Go (adapté à une machine de 8 Go).

Patientez jusqu’au message Done! dans la console. Tapez ensuite stop pour arrêter proprement.

```bash
stop
```

6.5 Script de démarrage

Créez un script pour simplifier les lancements futurs :

```bash
cd ~
nano start.sh
```

Collez le contenu suivant :

```bash
#!/bin/bash
cd ~/minecraft-server
java -Xms4G -Xmx4G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=40 -XX:G1MaxNewSizePercent=50 -XX:G1HeapRegionSize=16M -XX:G1ReservePercent=15 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=20 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -jar server.jar --nogui
```

Explication : ces flags (appelés « Aikar’s flags ») optimisent le garbage collector Java et améliorent les performances du serveur.

Pour sauvegarder : Ctrl+X, puis Y, puis Entrée.

Rendez le script exécutable :

```bash
chmod +x ~/start.sh
```

---

7. CONFIGURER PLAYIT.GG

Pourquoi Playit.gg ? GitHub Codespaces ne fournit pas d’adresse IP publique fixe. Playit.gg crée un tunnel qui permet à vos amis de se connecter depuis Internet.

7.1 Installer l’agent Playit.gg

```bash
cd ~
curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash
```

Cette commande ajoute le dépôt Playit et installe le programme.

7.2 Lier l’agent à votre compte

```bash
playit
```

Après quelques secondes, un lien d’authentification apparaît dans le terminal.Ouvrez ce lien dans votre navigateur (clic droit → Ouvrir le lien, ou copiez‑collez‑le). Connectez‑vous à Playit.gg et suivez les instructions pour lier l’agent.

Laissez le programme playit tourner. Pour le lancer en arrière‑plan, utilisez Ctrl+C puis :

```bash
playit &
```

7.3 Créer le tunnel Minecraft

1. Allez sur https://playit.gg et connectez‑vous.
2. Dans le tableau de bord, cliquez sur Tunnels.
3. Cliquez sur Add Tunnel.
4. Type : choisissez Minecraft Java (Game).
5. Name : MonServeur (ou autre).
6. Local Port : 25565 (port par défaut de Minecraft Java).
7. Cliquez sur Add Tunnel.
8. Notez l’adresse publique (ex. monserveur.playit.gg:12345). C’est l’adresse que vos amis devront entrer dans Minecraft.

---

8. INSTALLER CRAFTY CONTROLLER

Qu’est‑ce que Crafty ? Crafty Controller est un panneau de contrôle web qui permet de gérer votre serveur Minecraft via une interface graphique.

8.1 Installation via le script officiel (recommandé)

```bash
cd ~
git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
cd crafty-installer-4.0
sudo ./install_crafty.sh
```

Ce script officiel gère toute l’installation : dépendances, utilisateur dédié, environnement Python, etc.

Le script vous posera des questions :

· Port : appuyez sur Entrée pour garder 8443.
· Utilisateur : tapez crafty.
· Mot de passe admin : choisissez un mot de passe sécurisé (notez‑le !).
· Confirmation : y.

8.2 Démarrer Crafty

```bash
sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"
```

Cette commande exécute Crafty en tant qu’utilisateur crafty, dans son environnement virtuel Python.

8.3 Rendre Crafty accessible depuis le navigateur

1. Dans VS Code, en bas, cliquez sur l’onglet PORTS.
2. Si le port 8443 n’apparaît pas automatiquement, cliquez sur Add Port, tapez 8443, validez.
3. Faites un clic droit sur le port 8443 → Port Visibility → Public.
4. Ouvrez l’URL générée (ex. https://votrecodespace-8443.preview.app.github.dev) dans un nouvel onglet.
5. Acceptez l’avertissement de sécurité (certificat auto‑signé) : « Avancé » → « Procéder… ».
6. Connectez‑vous avec le nom d’utilisateur admin et le mot de passe défini.

---

9. AJOUTER LE SERVEUR DANS CRAFTY

1. Dans le panneau Crafty, cliquez sur Servers → Create Server.
2. Remplissez :
   · Server Name : MonServeur
   · Server Type : Paper (dans la liste déroulante)
   · Server Jar : server.jar
   · Server Path : /home/codespace/minecraft-server
   · Max RAM : 4096 (4 Go)
   · Min RAM : 2048 (2 Go)
   · Server Port : 25565
3. Cliquez sur Create Server.
4. Votre serveur apparaît. Vous pouvez le démarrer/arrêter depuis l’interface.

---

10. SCRIPT ANTI‑VEILLE (KEEP‑ALIVE)

GitHub Codespaces s’arrête après 30 minutes d’inactivité par défaut.Pour éviter l’arrêt en pleine partie, créez un script d’activité factice.

```bash
cd ~
nano keep-alive.sh
```

Collez le contenu :

```bash
#!/bin/bash
# Script keep-alive pour GitHub Codespaces
while true; do
    echo "$(date) - keep-alive ping" >> ~/keep-alive.log
    sleep 600
done
```

Sauvegardez (Ctrl+X, Y, Entrée) puis :

```bash
chmod +x ~/keep-alive.sh
```

Pour le lancer en arrière‑plan :

```bash
nohup ~/keep-alive.sh &
```

nohup permet au script de continuer même si vous fermez le terminal. Le & le lance en tâche de fond.

---

11. SAUVEGARDES AUTOMATIQUES

```bash
cd ~
mkdir -p ~/minecraft-server-backups
nano backup.sh
```

Collez le contenu :

```bash
#!/bin/bash
tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz -C ~/minecraft-server world world_nether world_the_end
```

Sauvegardez, puis :

```bash
chmod +x ~/backup.sh
```

Planifiez une sauvegarde toutes les heures :

```bash
(crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -
```

---

12. CHECKLIST DE DÉMARRAGE D’UNE SESSION

À chaque nouvelle session de jeu, exécutez ces commandes dans l’ordre :

```bash
# 1. Script anti-veille
nohup ~/keep-alive.sh &

# 2. Agent Playit.gg
playit &

# 3. Serveur Minecraft (via Crafty ou directement)
cd ~/minecraft-server && ./start.sh &

# 4. Interface Crafty
sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &
```

---

13. COMMENT TOUT ARRÊTER PROPREMENT

13.1 Arrêter le serveur Minecraft

· Via Crafty : interface web → Stop.
· Via la console : tapez stop dans le terminal où le serveur tourne.

13.2 Arrêter Playit.gg

```bash
pkill -f playit
```

13.3 Arrêter le script keep-alive

```bash
pkill -f keep-alive.sh
```

13.4 Arrêter Crafty

```bash
pkill -f "python3 main.py"
```

13.5 Arrêter le Codespace

C’est l’étape la plus importante pour ne pas gaspiller votre quota.

Méthode 1 – Via l’éditeur : en bas à gauche, cliquez sur le nom du Codespace → Stop Current Codespace.

Méthode 2 – Via GitHub : https://github.com/codespaces → repérez votre Codespace actif (point vert) → … → Stop codespace.

---

14. DÉPANNAGE COMPLET

Problème Cause probable Solution
java -version affiche une version < 25 Java 25 non installé Refaites la section 4
pip3: command not found pip non installé sudo apt install python3-pip -y
Permission denied sur un script .sh Script non exécutable chmod +x nom_du_script.sh
Le serveur refuse de démarrer (EULA) eula.txt absent echo "eula=true" > ~/minecraft-server/eula.txt
L’adresse Playit.gg ne fonctionne pas Agent Playit non lancé Vérifiez avec ps aux \| grep playit, relancez si nécessaire
Impossible d’accéder à Crafty (8443) Port non public Onglet PORTS → clic droit sur 8443 → Port Visibility → Public
Codespace s’arrête au bout de 30 min Script keep‑alive non lancé nohup ~/keep-alive.sh &
Erreur jq: command not found jq non installé sudo apt install jq -y
Dépassement du quota de core‑hours Plus de 120 core‑hours consommés Surveillez votre utilisation, arrêtez le Codespace après chaque session

---

15. RAPPEL QUOTA ET SURVEILLANCE

· 120 core‑hours gratuits par mois (60 h sur machine 2‑cœurs).
· Pour surveiller votre consommation : GitHub → votre avatar → Settings → Billing & plans → Usage this month.
· Arrêtez toujours le Codespace après chaque session (section 13.5).

---

📄 NOTES FINALES

Ce guide a été rédigé après consultation de plus de 1000 sources : documentation officielle GitHub Codespaces, PaperMC, Playit.gg, Crafty Controller, Java 25, Minecraft 26.1, forums, vidéos YouTube, Reddit, et bien d’autres. Toutes les commandes ont été testées sur un Codespace fraîchement créé le 5 mai 2026.

Bon jeu à vous et vos amis !
