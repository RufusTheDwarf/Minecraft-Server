# 🟩 Servidor Minecraft Grátis no GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ Este guia é destinado para uso educacional e privado. Rodar um servidor 24/7 no Codespaces não está de acordo com os Termos de Serviço do GitHub. O script anti-suspensão serve apenas para evitar desconexões *durante* uma sessão de jogo, respeitando a cota de 60 h/mês. Ou um certo Git baterá na sua porta às 3 da manhã...

---

## 📋 Índice

- [O que faremos](#-o-que-faremos)
- [O que você precisa](#-o-que-você-precisa)
- [Passo 0 - Entendendo as ferramentas](#-passo-0--entendendo-as-ferramentas)
- [Passo 1 - Criando as contas](#-passo-1--criando-as-contas)
- [Passo 2 - Criando o repositório e o Codespace](#-passo-2--criando-o-repositório-e-o-codespace)
- [Passo 3 - Se orientando no terminal](#-passo-3--se-orientando-no-terminal)
- [Passo 4 - Instalando o Java 21 LTS](#-passo-4--instalando-o-java-21-lts)
- [Passo 5 - Instalando o Python 3 e o pip](#-passo-5--instalando-o-python-3-e-o-pip)
- [Passo 6 - Baixando e preparando o PaperMC](#-passo-6--baixando-e-preparando-o-papermc)
- [Passo 7 - Configurando o Playit.gg](#-passo-7--configurando-o-playitgg)
- [Passo 8 - Instalando o Crafty Controller](#-passo-8--instalando-o-crafty-controller)
- [Passo 9 - Adicionando o servidor ao Crafty](#-passo-9--adicionando-o-servidor-ao-crafty)
- [Passo 10 - Script anti-suspensão](#-passo-10--script-anti-suspensão)
- [Passo 11 - Backups automáticos](#-passo-11--backups-automáticos)
- [🟢 Iniciando uma sessão](#-iniciando-uma-sessão)
- [🔴 Encerrando uma sessão](#-encerrando-uma-sessão)
- [Solução de problemas](#-solução-de-problemas)
- [Monitorando sua cota](#-monitorando-sua-cota)

---

## 🎯 O que faremos

Usar os créditos gratuitos do GitHub Codespaces para rodar um servidor Minecraft na nuvem, gerenciá-lo por uma interface web (Crafty Controller) e torná-lo acessível aos seus amigos pela internet sem mexer no seu roteador, graças ao Playit.gg.

Nenhum conhecimento prévio necessário. Cada comando é explicado.

---

## 🧰 O que você precisa

Tudo é gratuito.

| | Item | Detalhe |
|---|---|---|
| 🌐 | Um navegador web | Chrome, Firefox, Edge |
| 📧 | Um endereço de e-mail | Para criar as duas contas |
| 🐙 | Uma conta GitHub | Criada no Passo 1 |
| 🎮 | Uma conta Playit.gg | Criada no Passo 1 |
| ⏱️ | ~45 minutos | Para a primeira instalação |

> 💡 Uma vez configurado, reiniciar o servidor para uma nova sessão leva menos de 3 minutos.

---

## 🔍 Passo 0  Entendendo as ferramentas

Cinco minutos de leitura agora vão te poupar muita confusão depois.

| Ferramenta | Papel |
|---|---|
| **GitHub Codespaces** | Um computador Linux na nuvem, acessível pelo navegador. O plano gratuito oferece **120 core-hours/mês** → com a máquina de 2 núcleos, isso dá **60 horas reais de jogo**. |
| **PaperMC** | O motor do servidor. Versão melhorada do software oficial da Mojang: mais fluido, menos lag, compatível com plugins. |
| **Playit.gg** | O túnel. O GitHub não fornece um IP público. O Playit.gg cria um (`meuservidor.playit.gg`) que seus amigos digitam direto no Minecraft. |
| **Crafty Controller** | O painel de controle web. Iniciar, parar e monitorar o servidor com cliques. |

---

## 👤 Passo 1  Criando as contas

### 🐙 GitHub

1. Vá para [github.com/signup](https://github.com/signup)
2. Insira um e-mail, uma senha e um nome de usuário
3. Resolva o puzzle → **Create account**
4. Pegue o código de 6 dígitos no seu e-mail e insira

✅ Você vê seu nome de usuário no canto superior direito do painel do GitHub.

### 🎮 Playit.gg

1. Vá para [playit.gg](https://playit.gg)
2. **Login** → no final do formulário → **Sign up**
3. Preencha os campos e valide
4. Clique no link de confirmação recebido por e-mail

✅ Você pode acessar seu painel do Playit.gg.

---

## 🏗️ Passo 2  Criando o repositório e o Codespace

### O repositório

Um repositório é uma pasta de projeto no GitHub. Ele serve de base para criar o Codespace.

1. No GitHub: **`+`** canto superior direito → **New repository**
2. Preencha:
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ Você está na página do seu repositório `mc-server`.

### O Codespace

> ⚠️ **Passo crítico** - a escolha da máquina define sua cota. Escolher a errada reduz sua cota pela metade.

1. **`Menu`** → aba **Codespaces**
2. Clique no canto superior direito em **New Codespace**
3. Escolha o repositório que você criou para o servidor Minecraft
4. Escolha a região mais próxima de você (isso reduz o ping entre você e o servidor)
5. **Machine type** → **`2-core`** (8 GB RAM) - não escolha 4-core
6. **Create codespace** → aguarde 2-3 minutos

Um editor VS Code abre no seu navegador com um terminal na parte inferior.

✅ Você vê o prompt de comando no terminal.

---

## 💻 Passo 3  Se orientando no terminal

O terminal é onde você digita os comandos. Simplesmente copie e cole o que o guia indica.

| Comando | O que faz |
|---|---|
| `cd ~` | Voltar para a pasta pessoal |
| `cd ~/minecraft-server` | Ir para a pasta do servidor |
| `pwd` | Mostrar onde você está |
| `mkdir -p nome` | Criar uma pasta |
| `ls` | Listar arquivos |
| `sudo` | Executar como administrador |

> 💡 **Regra de ouro:** cada passo deste guia especifica de qual pasta executar o comando. Em caso de dúvida, digite `pwd`.

---

## ☕ Passo 4  Instalando o Java 21 (LTS)

O Minecraft é escrito em Java. A versão **21** é a recomendada pelo PaperMC. É a versão **LTS** (Long-Term Support): a mais estável, com manutenção mais longa. Existem versões mais novas, mas não são LTS.

📍 *De qualquer pasta.*

Primeiro, verifique se o Java já está presente:

    java -version

🔵 Se você vir `openjdk version "21.0.x"` → pule para o Passo 5.

Caso contrário:

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ O comando exibe `openjdk version "21.0.x"`.

---

## 🐍 Passo 5  Instalando o Python 3 e o pip

O Crafty Controller é desenvolvido em Python. Precisamos do Python 3 e do `pip` (seu gerenciador de pacotes) para instalá-lo e executá-lo.

📍 *Da sua pasta pessoal (`cd ~`).*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ Ambos os comandos exibem um número de versão sem erro.

---

## 🧱 Passo 6  Baixando e preparando o PaperMC

### Criar a pasta

📍 *Da sua pasta pessoal (`cd ~`).*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### Instalar o jq

O `jq` lê as respostas da API do PaperMC para buscar automaticamente a última build estável.

    sudo apt install jq -y

### Baixar o PaperMC

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 Se o comando falhar, use esta build fixa:
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` mostra `server.jar` na lista.

### Aceitar o EULA

> ⚠️ **Obrigação legal.** A Mojang exige a aceitação do Contrato de Licença de Usuário Final (EULA) antes de qualquer inicialização. Sem este arquivo, o servidor se recusa a iniciar. Ao executar o comando abaixo, você aceita os termos em [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

    echo "eula=true" > eula.txt

✅ `ls` mostra `eula.txt` ao lado de `server.jar`.

### Primeira execução de teste

    java -Xms2G -Xmx4G -jar server.jar --nogui

Espere a mensagem `Done!` (1-2 min) e depois pare:

    stop

✅ O servidor para de forma limpa e você recupera o prompt.

### Criar o script de inicialização

Esses parâmetros são chamados de *Aikar's flags*. Otimizações de memória reconhecidas pela comunidade que reduzem significativamente o lag.

📍 *Volte para sua pasta pessoal (`cd ~`).*

    nano start.sh

Cole:

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

Salve: **Ctrl+X** → **Y** → **Enter**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` mostra `-rwxr-xr-x` no início da linha.

---

## 📡 Passo 7  Configurando o Playit.gg

Seu Codespace não tem IP público. O Playit.gg cria um túnel e fornece um endereço que seus amigos digitam diretamente no Minecraft. Nenhuma configuração de rede sua.

📍 *Da sua pasta pessoal (`cd ~`).*

### Instalar o agente

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### Vincular o agente à sua conta

    playit

Um link de autenticação aparece no terminal. Abra no navegador → faça login → **Claim Agent**. Volte ao terminal → **Ctrl+C** → execute novamente em segundo plano:

    playit &

### Criar o túnel

1. No [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Preencha:
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MeuServidor`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 O endereço público é exibido (ex: `meuservidor.playit.gg:12345`). **Anote. É isso que você passa para os amigos.**

✅ O túnel aparece no painel com status "Connected".

---

## 🎛️ Passo 8  Instalando o Crafty Controller

O Crafty Controller é um painel de controle web: iniciar, parar, ver logs, gerenciar jogadores pela interface, sem linha de comando.

📍 *Da sua pasta pessoal (`cd ~`).*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

O script faz algumas perguntas:

| Pergunta | Resposta |
|---|---|
| Port | Pressione **Enter** (mantém `8443`) |
| User | `crafty` |
| Senha admin | Escolha uma e **anote** |
| Confirmation | `y` |

A instalação leva de 3 a 5 minutos.

### Iniciar o Crafty

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### Tornar a interface acessível

1. VS Code → aba **PORTS** na parte inferior
2. Se `8443` não aparecer → **Add Port** → `8443` → validar
3. Clique direito em `8443` → **Port Visibility** → **Public**
4. Abra a URL gerada em uma nova aba
5. Aviso de segurança → **Avançado** → **Prosseguir**
6. Faça login: `admin` + sua senha

✅ Você está no painel do Crafty Controller.

---

## 🔗 Passo 9  Adicionando o servidor ao Crafty

**Servers** → **Create Server** → preencha:

| Campo | Valor |
|---|---|
| Server Name | `MeuServidor` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 Na primeira inicialização, o Crafty pode exibir um pop-up para aceitar o EULA. Clique em **I Accept** e reinicie.

✅ O servidor muda para o status "Running" (verde) na interface.

---

## ⏳ Passo 10  Script anti-suspensão

Um Codespace para automaticamente após 30 minutos de inatividade. Este script envia um sinal a cada 10 minutos para manter a sessão ativa durante suas partidas.

📍 *Da sua pasta pessoal (`cd ~`).*

    nano keep-alive.sh

Cole:

    #!/bin/bash
    # Keep-alive para GitHub Codespaces
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Enter**, depois:

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` impede que o script pare se sua sessão fechar. O `&` executa em segundo plano.

✅ Após alguns minutos, `cat ~/keep-alive.log` mostra linhas com data e hora.

---

## 💾 Passo 11  Backups automáticos

Este script cria um arquivo compactado do seu mundo a cada hora. Em caso de corrupção, você restaura a partir de um backup recente.

📍 *Da sua pasta pessoal (`cd ~`).*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

Cole:

    #!/bin/bash
    # Backup automático do mundo Minecraft
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - Backup concluído." >> ~/backup.log

**Ctrl+X** → **Y** → **Enter**, depois:

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` mostra a linha agendada.

---

## 🟢 Iniciando uma sessão

> 📌 Toda vez que abrir o Codespace, copie e cole estes 4 comandos no terminal, nesta ordem.

    # 1. Anti-suspensão
    nohup ~/keep-alive.sh &

    # 2. Túnel Playit.gg
    playit &

    # 3. Servidor Minecraft
    cd ~/minecraft-server && ~/start.sh &

    # 4. Interface Crafty
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

Espere 1-2 minutos → verifique "Running" no Crafty → passe o endereço do Playit.gg para seus amigos. 🎮

---

## 🔴 Encerrando uma sessão

> ⚠️ **Fechar a aba não é suficiente.** O Codespace continua rodando em segundo plano e consome sua cota. Siga estes passos ao final de cada sessão.

**1. Parar o servidor Minecraft**

Via Crafty: clique no botão ⏹️ na interface.

Via terminal:

    kill $(pgrep -f "server.jar")

**2. Parar os processos em segundo plano**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Parar o Codespace** ← passo mais importante

Pelo GitHub (recomendado):
1. [github.com/codespaces](https://github.com/codespaces)
2. Seu Codespace ativo (🟢 ponto verde)
3. **`...`** → **Stop codespace**

Pelo editor: canto inferior esquerdo → nome do Codespace → **Stop Current Codespace**

✅ O ponto verde fica cinza. O Codespace está parado.

---

## 🆘 Solução de problemas

| Sintoma | Solução |
|---|---|
| ❌ `java -version` não mostra `21.x` | Refaça o Passo 4 do início |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` em um `.sh` | `chmod +x nome_script.sh` |
| ❌ Servidor não inicia (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ Endereço Playit.gg não funciona | `ps aux \| grep playit` → se ausente, reexecute: `playit &` |
| ❌ Crafty inacessível (porta 8443) | Aba **PORTS** → clique direito `8443` → **Port Visibility** → **Public** |
| ❌ Codespace para no meio do jogo | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` e repita o download |
| ❌ `OutOfMemoryError` nos logs | Verifique se a máquina é realmente **2-core / 8 GB RAM** |

Para qualquer outro problema: copie a mensagem de erro exata e cole no [Stack Overflow](https://stackoverflow.com) com a tag `[minecraft]` ou `[github-codespaces]`. Comunidades: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 Monitorando sua cota

O GitHub oferece **120 core-hours grátis por mês**. Com a máquina de 2 núcleos, cada hora de jogo consome 2 → **60 horas reais por mês**.

Para ver seu uso: **avatar do GitHub** → **Settings** → **Billing & plans** → **Usage this month** → linha **Codespaces**

> ⚠️ Se estiver se aproximando de 120 core-hours, pare o Codespace imediatamente e aguarde a renovação mensal.

---

## 📎 Recursos

- [Documentação PaperMC](https://docs.papermc.io)
- [Documentação Crafty Controller](https://docs.craftycontrol.com)
- [Documentação Playit.gg](https://playit.gg/support)
- [Documentação GitHub Codespaces](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*Testado em um Codespace recém-criado - maio de 2026.*
