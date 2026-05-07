# ⛏️ Serveur Minecraft Gratuit — GitHub Codespaces

> **Zéro euro. Zéro installation. Zéro prise de tête.**  
> Un serveur Minecraft performant dans le cloud, opérationnel en moins d'une heure.

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/Serveur-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/Panel-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/Tunnel-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![Licence MIT](https://img.shields.io/badge/Licence-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ Vue d'ensemble

Ce dépôt est un **guide complet, pas-à-pas et intégralement vérifié** pour héberger votre propre serveur Minecraft **gratuitement** sur GitHub Codespaces.

Vous et vos amis pouvez jouer ensemble sur un serveur performant, accessible depuis n'importe où dans le monde **sans dépenser un centime**, en restant dans les quotas gratuits de GitHub.

```
Navigateur web → GitHub Codespace (Linux) → PaperMC → Playit.gg → Vos amis 🎮
```

**Ce que vous obtenez :**
- 🖥️ **Machine virtuelle Linux** dans le cloud (2 cœurs, 8 Go RAM, 32 Go stockage)
- 🟢 **PaperMC** - le serveur Minecraft le plus optimisé et stable du marché
- 🧭 **Crafty Controller** - panneau web pour gérer le serveur en quelques clics
- 🌐 **Playit.gg** - tunnel public pour connecter vos amis sans configuration réseau
- 💾 **Sauvegardes automatiques** et **script anti-veille** inclus

---

## 🎯 Pour qui ?

**Tout le monde.** Ce guide est rédigé de manière pédagogique et rassurante.

| Votre profil | Ce guide vous convient ? |
|---|---|
| Débutant complet, jamais touché à Linux | ✅ Oui - tout est expliqué, justifié |
| Habitué du terminal | ✅ Oui - allez à l'essentiel |
| Sans expérience en réseau ou administration | ✅ Oui - Playit.gg gère ça pour vous |
| Sans budget | ✅ Oui - 100% gratuit dans les quotas |

> Si vous savez **copier-coller** et **suivre des instructions**, vous pouvez créer ce serveur.

---

## ⚡ Prérequis

Vous avez besoin **uniquement** de :

- [ ] Un **navigateur web** (Chrome, Firefox, Edge…)
- [ ] Un **compte GitHub** gratuit - [s'inscrire ici](https://github.com/signup)
- [ ] Un **compte Playit.gg** gratuit - [s'inscrire ici](https://playit.gg)

**Aucun logiciel à installer sur votre machine.**

---

## 📂 Fichiers du dépôt ( À venir )

⚠️ Section actuellement en construction.
Les informations ci-dessous ne sont que des prévisions.
Voir le guide dans le dossier [`Docs`](Docs)

| Fichier | Rôle |
|---|---|
| `README.md` | Ce fichier - vue d'ensemble du projet |
| `GUIDE.md` | 📘 **Le guide complet**, étape par étape |
| `start.sh` | Lance le serveur avec les optimisations Aikar's Flags |
| `keep-alive.sh` | Empêche le Codespace de s'endormir automatiquement |
| `backup.sh` | Sauvegarde automatique du monde Minecraft |

---

## 🚀 Démarrage rapide ( À venir )

⚠️ Section actuellement en construction.
Les informations ci-dessous ne sont que des prévisions.
Voir le guide dans le dossier [`Docs`](Docs)


```bash
# 1. Clonez ce dépôt dans un Codespace GitHub
# 2. Installez Java 21
sudo apt-get install -y openjdk-21-jdk

# 3. Lancez le serveur
bash start.sh

# 4. Démarrez le tunnel Playit.gg (dans un second terminal)
./playit

# 5. Ouvrez Crafty Controller sur le port 8443
```

> **Pour le guide détaillé, voir [`FR_GUIDE.md`](../Docs/FR_Guide.md).**

---

## 🗂️ Contenu du guide

Le fichier `FR_GUIDE.md` couvre les 17 étapes suivantes :

1. Introduction et matériel requis
2. Comprendre les outils (Codespaces, PaperMC, Crafty, Playit.gg)
3. Création des comptes GitHub et Playit.gg
4. Création du dépôt et du Codespace
5. Apprivoiser le terminal Linux
6. Installation de Java 21
7. Installation de Python 3 et pip
8. Téléchargement et configuration de PaperMC
9. Configuration de Playit.gg
10. Installation de Crafty Controller
11. Ajout du serveur dans Crafty
12. Script anti-veille (keep-alive)
13. Sauvegardes automatiques
14. ✅ Checklist de démarrage de session
15. 🛑 Checklist d'arrêt de session
16. Dépannage et support
17. Surveillance du quota mensuel

Chaque étape contient : l'explication du *pourquoi*, les commandes exactes à copier, et une vérification pour s'assurer que tout fonctionne.

---

## ⚠️ Limites & Usage responsable

### Quota gratuit GitHub Codespaces

```
120 core‑hours / mois  →  60 heures de jeu sur une machine 2 cœurs
```

| À faire | À éviter |
|---|---|
| ✅ Stopper le Codespace après chaque session | ❌ Laisser tourner 24h/24 |
| ✅ Surveiller Settings › Billing & plans | ❌ Ignorer votre consommation |
| ✅ Utiliser pour des sessions ponctuelles | ❌ Usage en production continu |

> ⚠️ Faire tourner un serveur de jeux en continu n'est **pas conforme** aux conditions d'utilisation de GitHub Codespaces. Ce guide est conçu pour un usage ponctuel et responsable.

### Stockage
- **32 Go** disponibles sur la machine 2 cœurs
- Les données **non versionnées** sont perdues si le Codespace est supprimé
- Utilisez `backup.sh` et commitez régulièrement vos sauvegardes

---

## 🤝 Contribuer

Ce guide est maintenu avec soin, mais les erreurs arrivent. Vous avez repéré une coquille, une commande obsolète ou un point à améliorer ?

1. **Ouvrez une [Issue](../../issues)** pour signaler le problème
2. **Proposez une [Pull Request](../../pulls)** avec vos corrections

---

## 💬 Support & Communauté

| Ressource | Pour |
|---|---|
| [Discord PaperMC](https://discord.gg/papermc) | Questions sur le serveur Minecraft |
| [Discord Playit.gg](https://discord.gg/playit) | Problèmes de tunnel réseau |
| [Stack Overflow](https://stackoverflow.com) | Erreurs Linux / Java tags `[minecraft]` `[github-codespaces]` |
| [Issues GitHub](../../issues) | Problèmes spécifiques à ce guide |

---

## 📄 Licence

Distribué sous licence **MIT**. Libre d'utilisation, modification et redistribution avec conservation de la notice de copyright.

---

<div align="center">

**Prêt à jouer ?**

### 👉 [Ouvrir le guide complet - GUIDE.md](Tutorial/🇨🇵Fr_Guide.md)

*Merci aux communautés PaperMC, Crafty Controller, Playit.gg et GitHub.*

</div>
