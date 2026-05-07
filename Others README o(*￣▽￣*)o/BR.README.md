# ⛏️ Servidor Minecraft Grátis - GitHub Codespaces

> **Zero euros. Zero instalação. Zero complicação.**  
> Um servidor Minecraft de alto desempenho na nuvem, pronto em menos de uma hora.

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/Servidor-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/Painel-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/Túnel-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![Licença MIT](https://img.shields.io/badge/Licença-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ Visão geral

Este repositório é um **guia completo, passo a passo e totalmente verificado** para hospedar seu próprio servidor Minecraft **gratuitamente** no GitHub Codespaces.

Você e seus amigos podem jogar juntos em um servidor potente, acessível de qualquer lugar do mundo **sem gastar um centavo**, respeitando as cotas gratuitas do GitHub.

    Navegador web → GitHub Codespace (Linux) → PaperMC → Playit.gg → Seus amigos 🎮

**O que você ganha:**
- 🖥️ **Máquina virtual Linux** na nuvem (2 núcleos, 8 GB RAM, 32 GB armazenamento)
- 🟢 **PaperMC** - o servidor Minecraft mais otimizado e estável do mercado
- 🧭 **Crafty Controller** - painel web para gerenciar o servidor com poucos cliques
- 🌐 **Playit.gg** - túnel público para conectar seus amigos sem configurar rede
- 💾 **Backups automáticos** e **script anti‑suspensão** inclusos

---

## 🎯 Para quem?

**Para todo mundo.** Este guia foi escrito de forma didática e tranquilizadora.

| Seu perfil | Este guia serve para você? |
|---|---|
| Iniciante completo, nunca mexeu com Linux | ✅ Sim - tudo está explicado e justificado |
| Acostumado com o terminal | ✅ Sim - vá direto ao essencial |
| Sem experiência em redes ou administração | ✅ Sim - o Playit.gg resolve isso por você |
| Sem orçamento | ✅ Sim - 100% gratuito dentro das cotas |

> Se você sabe **copiar e colar** e **seguir instruções**, você consegue criar este servidor.

---

## ⚡ Pré‑requisitos

Você precisa apenas de:

- [ ] Um **navegador web** (Chrome, Firefox, Edge…)
- [ ] Uma **conta GitHub** gratuita – [criar conta aqui](https://github.com/signup)
- [ ] Uma **conta Playit.gg** gratuita – [criar conta aqui](https://playit.gg)

**Nenhum software para instalar na sua máquina.**

---

## 📂 Arquivos do repositório (Em breve)

⚠️ Esta seção está em construção.  
As informações abaixo são apenas uma prévia.  
Consulte o guia na pasta [`Docs`](../Docs).

| Arquivo | Função |
|---|---|
| `README.md` | Este arquivo - visão geral do projeto |
| `GUIDE.md` | 📘 **O guia completo**, passo a passo |
| `start.sh` | Inicia o servidor com as otimizações Aikar’s Flags |
| `keep-alive.sh` | Impede que o Codespace entre em suspensão automaticamente |
| `backup.sh` | Backup automático do mundo Minecraft |

---

## 🚀 Início rápido (Em breve)

⚠️ Esta seção está em construção.  
As informações abaixo são apenas uma prévia.  
Consulte o guia na pasta [`Docs`](../Docs).

    # 1. Clone este repositório em um Codespace do GitHub
    # 2. Instale o Java 21
    sudo apt-get install -y openjdk-21-jdk

    # 3. Inicie o servidor
    bash start.sh

    # 4. Inicie o túnel Playit.gg (em um segundo terminal)
    ./playit

    # 5. Abra o Crafty Controller na porta 8443

> **Para o guia detalhado, veja [`BR_GUIDE.md`](../Docs/BR_Guide.md).**

---

## 🗂️ Conteúdo do guia

O arquivo `BR_GUIDE.md` aborda as 17 etapas a seguir:

1. Introdução e requisitos de hardware
2. Entendendo as ferramentas (Codespaces, PaperMC, Crafty, Playit.gg)
3. Criando as contas GitHub e Playit.gg
4. Criando o repositório e o Codespace
5. Familiarizando‑se com o terminal Linux
6. Instalando o Java 21
7. Instalando Python 3 e pip
8. Baixando e configurando o PaperMC
9. Configurando o Playit.gg
10. Instalando o Crafty Controller
11. Adicionando o servidor ao Crafty
12. Script anti‑suspensão (keep‑alive)
13. Backups automáticos
14. ✅ Checklist de início de sessão
15. 🛑 Checklist de parada de sessão
16. Solução de problemas e suporte
17. Monitoramento da cota mensal

Cada etapa inclui: a explicação do *porquê*, os comandos exatos para copiar e uma verificação para garantir que tudo funciona.

---

## ⚠️ Limitações e uso responsável

### Cota gratuita do GitHub Codespaces

    120 core‑hours / mês  →  60 horas de jogo em uma máquina de 2 núcleos

| Fazer | Evitar |
|---|---|
| ✅ Parar o Codespace após cada sessão | ❌ Deixar rodando 24h por dia |
| ✅ Verificar Settings › Billing & plans | ❌ Ignorar seu consumo |
| ✅ Usar para sessões pontuais | ❌ Uso contínuo em produção |

> ⚠️ Manter um servidor de jogos funcionando continuamente **não está em conformidade** com os termos de uso do GitHub Codespaces. Este guia foi feito para uso esporádico e responsável.

### Armazenamento
- **32 GB** disponíveis na máquina de 2 núcleos
- Dados **não versionados** são perdidos se o Codespace for excluído
- Use `backup.sh` e faça commit dos seus backups regularmente

---

## 🤝 Contribuindo

Este guia é mantido com cuidado, mas erros acontecem. Encontrou um erro de digitação, um comando desatualizado ou algo que pode melhorar?

1. **Abra uma [Issue](../../../issues)** para relatar o problema
2. **Envie uma [Pull Request](../../../pulls)** com suas correções

---

## 💬 Suporte e comunidade

| Recurso | Para |
|---|---|
| [Discord PaperMC](https://discord.gg/papermc) | Perguntas sobre o servidor Minecraft |
| [Discord Playit.gg](https://discord.gg/playit) | Problemas de túnel / rede |
| [Stack Overflow](https://stackoverflow.com) | Erros Linux / Java com tags `[minecraft]` `[github-codespaces]` |
| [Issues GitHub](../../issues) | Problemas específicos deste guia |

---

## 📄 Licença

Distribuído sob a licença **MIT**. Livre para usar, modificar e redistribuir, mantendo o aviso de direitos autorais.

---

<div align="center">

**Pronto para jogar?**

### 👉 [Abrir o guia completo - BR_Guide.md](Tutorial/🇧🇷Br_Guide.md)

*Agradecemos às comunidades PaperMC, Crafty Controller, Playit.gg e GitHub.*

</div>
