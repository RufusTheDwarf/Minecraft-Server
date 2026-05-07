# 🟩 Servidor Minecraft Gratis en GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ Esta guía está pensada para un uso educativo y privado. Tener un servidor 24/7 en Codespaces no cumple con los Términos de Servicio de GitHub. El script anti-suspensión solo evita desconexiones *durante* una sesión de juego, dentro de la cuota de 60 h/mes. O un tal Git llamará a tu puerta a las 3 AM...

---

## 📋 Tabla de contenidos

- [Qué vamos a hacer](#-qué-vamos-a-hacer)
- [Qué necesitas](#-qué-necesitas)
- [Paso 0 - Entender las herramientas](#-paso-0--entender-las-herramientas)
- [Paso 1 - Crear las cuentas](#-paso-1--crear-las-cuentas)
- [Paso 2 - Crear el repositorio y el Codespace](#-paso-2--crear-el-repositorio-y-el-codespace)
- [Paso 3 - Orientarse en la terminal](#-paso-3--orientarse-en-la-terminal)
- [Paso 4 - Instalar Java 21 LTS](#-paso-4--instalar-java-21-lts)
- [Paso 5 - Instalar Python 3 y pip](#-paso-5--instalar-python-3-y-pip)
- [Paso 6 - Descargar y preparar PaperMC](#-paso-6--descargar-y-preparar-papermc)
- [Paso 7 - Configurar Playit.gg](#-paso-7--configurar-playitgg)
- [Paso 8 - Instalar Crafty Controller](#-paso-8--instalar-crafty-controller)
- [Paso 9 - Añadir el servidor a Crafty](#-paso-9--añadir-el-servidor-a-crafty)
- [Paso 10 - Script anti-suspensión](#-paso-10--script-anti-suspensión)
- [Paso 11 - Copias de seguridad automáticas](#-paso-11--copias-de-seguridad-automáticas)
- [🟢 Iniciar una sesión](#-iniciar-una-sesión)
- [🔴 Detener una sesión](#-detener-una-sesión)
- [Solución de problemas](#-solución-de-problemas)
- [Controlar tu cuota](#-controlar-tu-cuota)

---

## 🎯 Qué vamos a hacer

Usar los créditos gratuitos de GitHub Codespaces para ejecutar un servidor Minecraft en la nube, administrarlo mediante una interfaz web (Crafty Controller) y hacerlo accesible a tus amigos por Internet sin tocar tu router, gracias a Playit.gg.

No se requieren conocimientos previos. Cada comando está explicado.

---

## 🧰 Qué necesitas

Todo es gratis.

| | Elemento | Detalle |
|---|---|---|
| 🌐 | Un navegador web | Chrome, Firefox, Edge |
| 📧 | Una dirección de correo | Para crear las dos cuentas |
| 🐙 | Una cuenta de GitHub | Se crea en el Paso 1 |
| 🎮 | Una cuenta de Playit.gg | Se crea en el Paso 1 |
| ⏱️ | ~45 minutos | Para la primera instalación |

> 💡 Una vez configurado, reiniciar el servidor para una nueva sesión lleva menos de 3 minutos.

---

## 🔍 Paso 0  Entender las herramientas

Cinco minutos de lectura ahora te ahorrarán mucha confusión después.

| Herramienta | Función |
|---|---|
| **GitHub Codespaces** | Un ordenador Linux en la nube, accesible desde el navegador. El plan gratuito da **120 core-hours/mes** → con la máquina de 2 núcleos, son **60 horas reales de juego**. |
| **PaperMC** | El motor del servidor. Versión mejorada del software oficial de Mojang: más fluido, menos lag, compatible con plugins. |
| **Playit.gg** | El túnel. GitHub no da una IP pública. Playit.gg crea una (`miservidor.playit.gg`) que tus amigos introducen directamente en Minecraft. |
| **Crafty Controller** | El panel de control web. Iniciar, detener y supervisar el servidor con clics. |

---

## 👤 Paso 1  Crear las cuentas

### 🐙 GitHub

1. Ve a [github.com/signup](https://github.com/signup)
2. Ingresa un correo, una contraseña y un nombre de usuario
3. Resuelve el puzzle → **Create account**
4. Recupera el código de 6 dígitos de tu bandeja de entrada e ingrésalo

✅ Ves tu nombre de usuario en la esquina superior derecha del panel de GitHub.

### 🎮 Playit.gg

1. Ve a [playit.gg](https://playit.gg)
2. **Login** → al final del formulario → **Sign up**
3. Rellena los campos y valida
4. Haz clic en el enlace de confirmación recibido por correo

✅ Puedes acceder a tu panel de Playit.gg.

---

## 🏗️ Paso 2  Crear el repositorio y el Codespace

### El repositorio

Un repositorio es una carpeta de proyecto en GitHub. Sirve como base para crear el Codespace.

1. En GitHub: **`+`** arriba a la derecha → **New repository**
2. Rellena:
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ Estás en la página de tu repositorio `mc-server`.

### El Codespace

> ⚠️ **Paso crítico** - la elección de la máquina determina tu cuota. Equivocarse aquí la divide a la mitad.

1. **`Menú`** → pestaña **Codespaces**
2. Arriba a la derecha **New Codespace**
3. Elige el repositorio que creaste para el servidor Minecraft
4. Elige la región más cercana a ti (esto reduce el ping entre tú y el servidor)
5. **Machine type** → **`2-core`** (8 GB RAM) - no elijas 4-core
6. **Create codespace** → espera 2-3 minutos

Se abre un editor VS Code en tu navegador con una terminal en la parte inferior.

✅ Ves el prompt de comandos en la terminal.

---

## 💻 Paso 3  Orientarse en la terminal

La terminal es donde escribes los comandos. Simplemente copia y pega lo que indica la guía.

| Comando | Qué hace |
|---|---|
| `cd ~` | Volver a la carpeta personal |
| `cd ~/minecraft-server` | Ir a la carpeta del servidor |
| `pwd` | Mostrar dónde estás |
| `mkdir -p nombre` | Crear una carpeta |
| `ls` | Listar archivos |
| `sudo` | Ejecutar como administrador |

> 💡 **Regla de oro:** cada paso de esta guía especifica desde qué carpeta ejecutar el comando. En caso de duda, escribe `pwd`.

---

## ☕ Paso 4  Instalar Java 21 (LTS)

Minecraft está escrito en Java. La versión **21** es la recomendada por PaperMC. Es la versión **LTS** (Long-Term Support): la más estable, la que recibe mantenimiento por más tiempo. Existen versiones más nuevas, pero no son LTS.

📍 *Desde cualquier carpeta.*

Primero, comprueba si Java ya está instalado:

    java -version

🔵 Si ves `openjdk version "21.0.x"` → salta al Paso 5.

Si no:

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ El comando muestra `openjdk version "21.0.x"`.

---

## 🐍 Paso 5  Instalar Python 3 y pip

Crafty Controller está desarrollado en Python. Necesitamos Python 3 y `pip` (su gestor de paquetes) para instalarlo y ejecutarlo.

📍 *Desde tu carpeta personal (`cd ~`).*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ Ambos comandos muestran un número de versión sin errores.

---

## 🧱 Paso 6  Descargar y preparar PaperMC

### Crear la carpeta

📍 *Desde tu carpeta personal (`cd ~`).*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### Instalar jq

`jq` lee las respuestas de la API de PaperMC para obtener automáticamente la última build estable.

    sudo apt install jq -y

### Descargar PaperMC

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 Si el comando falla, usa esta build fija:
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` muestra `server.jar` en la lista.

### Aceptar el EULA

> ⚠️ **Obligación legal.** Mojang exige la aceptación del Acuerdo de Licencia de Usuario Final (EULA) antes de cualquier inicio. Sin este archivo, el servidor se niega a arrancar. Al ejecutar el siguiente comando, aceptas los términos en [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

    echo "eula=true" > eula.txt

✅ `ls` muestra `eula.txt` junto a `server.jar`.

### Primer lanzamiento de prueba

    java -Xms2G -Xmx4G -jar server.jar --nogui

Espera el mensaje `Done!` (1-2 min), luego detén:

    stop

✅ El servidor se detiene limpiamente y recuperas el prompt.

### Crear el script de inicio

Estos parámetros se llaman *Aikar's flags*. Optimizaciones de memoria reconocidas por la comunidad de Minecraft que reducen significativamente el lag.

📍 *Vuelve a tu carpeta personal (`cd ~`).*

    nano start.sh

Pega:

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

Guardar: **Ctrl+X** → **Y** → **Enter**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` muestra `-rwxr-xr-x` al principio de la línea.

---

## 📡 Paso 7  Configurar Playit.gg

Tu Codespace no tiene IP pública. Playit.gg crea un túnel y te proporciona una dirección que tus amigos introducen directamente en Minecraft. Sin configuración de red por tu parte.

📍 *Desde tu carpeta personal (`cd ~`).*

### Instalar el agente

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### Vincular el agente a tu cuenta

    playit

Aparece un enlace de autenticación en la terminal. Ábrelo en tu navegador → inicia sesión → **Claim Agent**. Vuelve a la terminal → **Ctrl+C** → relanza en segundo plano:

    playit &

### Crear el túnel

1. En [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Rellena:
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MiServidor`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 La dirección pública se muestra (ej. `miservidor.playit.gg:12345`). **Anótala. Es lo que darás a tus amigos.**

✅ El túnel aparece en el panel con el estado "Connected".

---

## 🎛️ Paso 8  Instalar Crafty Controller

Crafty Controller es un panel de control web: iniciar, detener, ver logs, gestionar jugadores desde una interfaz, sin línea de comandos.

📍 *Desde tu carpeta personal (`cd ~`).*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

El script hace algunas preguntas:

| Pregunta | Respuesta |
|---|---|
| Puerto | Pulsa **Enter** (mantiene `8443`) |
| Usuario | `crafty` |
| Contraseña admin | Elige una y **anótala** |
| Confirmación | `y` |

La instalación tarda 3-5 minutos.

### Iniciar Crafty

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### Hacer accesible la interfaz

1. VS Code → pestaña **PORTS** abajo
2. Si `8443` no aparece → **Add Port** → `8443` → valida
3. Clic derecho en `8443` → **Port Visibility** → **Public**
4. Abre la URL generada en una pestaña nueva
5. Aviso de seguridad → **Avanzado** → **Proceder**
6. Inicia sesión: `admin` + tu contraseña

✅ Estás en el panel de Crafty Controller.

---

## 🔗 Paso 9  Añadir el servidor a Crafty

**Servers** → **Create Server** → rellena:

| Campo | Valor |
|---|---|
| Server Name | `MiServidor` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 En el primer arranque, Crafty puede mostrar un pop-up para aceptar el EULA. Haz clic en **I Accept** y luego reinicia.

✅ El servidor pasa a estado "Running" (verde) en la interfaz.

---

## ⏳ Paso 10  Script anti-suspensión

Un Codespace se detiene automáticamente tras 30 minutos de inactividad. Este script envía una señal cada 10 minutos para mantener la sesión activa durante tus partidas.

📍 *Desde tu carpeta personal (`cd ~`).*

    nano keep-alive.sh

Pega:

    #!/bin/bash
    # Keep-alive para GitHub Codespaces
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Enter**, luego:

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` evita que el script se detenga si se cierra la sesión. `&` lo ejecuta en segundo plano.

✅ Después de unos minutos, `cat ~/keep-alive.log` muestra líneas con marca de tiempo.

---

## 💾 Paso 11  Copias de seguridad automáticas

Este script crea un archivo comprimido de tu mundo cada hora. En caso de corrupción, puedes volver a una copia reciente.

📍 *Desde tu carpeta personal (`cd ~`).*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

Pega:

    #!/bin/bash
    # Copia de seguridad automática del mundo Minecraft
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - Copia de seguridad completada." >> ~/backup.log

**Ctrl+X** → **Y** → **Enter**, luego:

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` muestra la línea programada.

---

## 🟢 Iniciar una sesión

> 📌 Cada vez que abras el Codespace, copia y pega estos 4 comandos en la terminal en este orden.

    # 1. Anti-suspensión
    nohup ~/keep-alive.sh &

    # 2. Túnel Playit.gg
    playit &

    # 3. Servidor Minecraft
    cd ~/minecraft-server && ~/start.sh &

    # 4. Interfaz Crafty
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

Espera 1-2 minutos → verifica "Running" en Crafty → da la dirección Playit.gg a tus amigos. 🎮

---

## 🔴 Detener una sesión

> ⚠️ **Cerrar la pestaña no es suficiente.** El Codespace sigue ejecutándose en segundo plano y consume tu cuota. Sigue estos pasos al final de cada sesión.

**1. Detener el servidor Minecraft**

Vía Crafty: haz clic en el botón ⏹️ de la interfaz.

Vía terminal:

    kill $(pgrep -f "server.jar")

**2. Detener procesos en segundo plano**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Detener el Codespace** ← paso más importante

Desde GitHub (recomendado):
1. [github.com/codespaces](https://github.com/codespaces)
2. Tu Codespace activo (🟢 punto verde)
3. **`...`** → **Stop codespace**

Desde el editor: abajo a la izquierda → nombre del Codespace → **Stop Current Codespace**

✅ El punto verde se vuelve gris. El Codespace está detenido.

---

## 🆘 Solución de problemas

| Síntoma | Solución |
|---|---|
| ❌ `java -version` no muestra `21.x` | Rehaz el Paso 4 desde el principio |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` en un `.sh` | `chmod +x nombre_script.sh` |
| ❌ El servidor no arranca (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ La dirección Playit.gg no funciona | `ps aux \| grep playit` → si falta, relanza: `playit &` |
| ❌ Crafty no accesible (puerto 8443) | Pestaña **PORTS** → clic derecho `8443` → **Port Visibility** → **Public** |
| ❌ Codespace se detiene en plena partida | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` y reintenta la descarga |
| ❌ `OutOfMemoryError` en logs | Verifica que la máquina es **2-core / 8 GB RAM** |

Para cualquier otro problema: copia el mensaje de error exacto en [Stack Overflow](https://stackoverflow.com) con la etiqueta `[minecraft]` o `[github-codespaces]`. Comunidades: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 Controlar tu cuota

GitHub ofrece **120 core-hours gratis al mes**. Con la máquina de 2 núcleos, cada hora de juego consume 2 → **60 horas reales al mes**.

Para ver tu consumo: **avatar de GitHub** → **Settings** → **Billing & plans** → **Usage this month** → línea **Codespaces**

> ⚠️ Si te acercas a 120 core-hours, detén el Codespace inmediatamente y espera la renovación mensual.

---

## 📎 Recursos

- [Documentación PaperMC](https://docs.papermc.io)
- [Documentación Crafty Controller](https://docs.craftycontrol.com)
- [Documentación Playit.gg](https://playit.gg/support)
- [Documentación GitHub Codespaces](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*Probado en un Codespace recién creado - mayo 2026.*
