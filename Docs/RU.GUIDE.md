# 🟩 Бесплатный сервер Minecraft на GitHub Codespaces

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ Это руководство предназначено для образовательных и частных целей. Круглосуточная работа сервера в Codespaces не соответствует условиям использования GitHub. Скрипт предотвращения сна нужен только для предотвращения отключений *во время* игровой сессии, в пределах квоты 60 ч/мес. Иначе некий Git постучится к вам в дверь в 3 часа ночи...

---

## 📋 Содержание

- [Что мы будем делать](#-что-мы-будем-делать)
- [Что вам понадобится](#-что-вам-понадобится)
- [Шаг 0 - Понимание инструментов](#-шаг-0--понимание-инструментов)
- [Шаг 1 - Создание учётных записей](#-шаг-1--создание-учётных-записей)
- [Шаг 2 - Создание репозитория и Codespace](#-шаг-2--создание-репозитория-и-codespace)
- [Шаг 3 - Ориентация в терминале](#-шаг-3--ориентация-в-терминале)
- [Шаг 4 - Установка Java 21 LTS](#-шаг-4--установка-java-21-lts)
- [Шаг 5 - Установка Python 3 и pip](#-шаг-5--установка-python-3-и-pip)
- [Шаг 6 - Загрузка и настройка PaperMC](#-шаг-6--загрузка-и-настройка-papermc)
- [Шаг 7 - Настройка Playit.gg](#-шаг-7--настройка-playitgg)
- [Шаг 8 - Установка Crafty Controller](#-шаг-8--установка-crafty-controller)
- [Шаг 9 - Добавление сервера в Crafty](#-шаг-9--добавление-сервера-в-crafty)
- [Шаг 10 - Скрипт предотвращения сна](#-шаг-10--скрипт-предотвращения-сна)
- [Шаг 11 - Автоматические резервные копии](#-шаг-11--автоматические-резервные-копии)
- [🟢 Запуск сессии](#-запуск-сессии)
- [🔴 Остановка сессии](#-остановка-сессии)
- [Устранение неполадок](#-устранение-неполадок)
- [Контроль квоты](#-контроль-квоты)

---

## 🎯 Что мы будем делать

Использовать бесплатные кредиты GitHub Codespaces для запуска сервера Minecraft в облаке, управлять им через веб-интерфейс (Crafty Controller) и сделать его доступным для друзей через интернет, не трогая роутер, благодаря Playit.gg.

Никаких предварительных знаний не требуется. Каждая команда объяснена.

---

## 🧰 Что вам понадобится

Всё бесплатно.

| | Элемент | Описание |
|---|---|---|
| 🌐 | Веб-браузер | Chrome, Firefox, Edge |
| 📧 | Адрес электронной почты | Для создания двух учётных записей |
| 🐙 | Учётная запись GitHub | Создаётся в Шаге 1 |
| 🎮 | Учётная запись Playit.gg | Создаётся в Шаге 1 |
| ⏱️ | ~45 минут | На первую установку |

> 💡 После настройки перезапуск сервера для новой сессии занимает менее 3 минут.

---

## 🔍 Шаг 0  Понимание инструментов

Пять минут чтения сейчас уберегут вас от массы путаницы впоследствии.

| Инструмент | Роль |
|---|---|
| **GitHub Codespaces** | Linux-компьютер в облаке, доступный из браузера. Бесплатный тариф даёт **120 ядро-часов/мес** → с 2-ядерной машиной это **60 реальных часов игры**. |
| **PaperMC** | Движок сервера. Улучшенная версия официального ПО Mojang: плавнее, меньше лагов, совместимость с плагинами. |
| **Playit.gg** | Туннель. GitHub не даёт публичный IP. Playit.gg создаёт адрес (`myserver.playit.gg`), который друзья вводят прямо в Minecraft. |
| **Crafty Controller** | Панель веб-управления. Запуск, остановка, мониторинг сервера по клику. |

---

## 👤 Шаг 1  Создание учётных записей

### 🐙 GitHub

1. Перейдите на [github.com/signup](https://github.com/signup)
2. Введите email, пароль и имя пользователя
3. Решите головоломку → **Create account**
4. Получите 6-значный код из письма и введите его

✅ В правом верхнем углу панели GitHub отображается ваше имя пользователя.

### 🎮 Playit.gg

1. Перейдите на [playit.gg](https://playit.gg)
2. **Login** → внизу формы → **Sign up**
3. Заполните поля и подтвердите
4. Нажмите на ссылку подтверждения из письма

✅ Вы можете зайти в свою панель Playit.gg.

---

## 🏗️ Шаг 2  Создание репозитория и Codespace

### Репозиторий

Репозиторий — это папка проекта на GitHub. Он служит основой для Codespace.

1. На GitHub: **`+`** вверху справа → **New repository**
2. Заполните:
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ Вы на странице своего репозитория `mc-server`.

### Codespace

> ⚠️ **Критический шаг** — выбор машины определяет вашу квоту. Ошибка здесь уменьшает её вдвое.

1. **`Меню`** → вкладка **Codespaces**
2. Вверху справа нажмите **New Codespace**
3. Выберите репозиторий, созданный для сервера Minecraft
4. Выберите ближайший к вам регион (это уменьшит пинг между вами и сервером)
5. **Machine type** → **`2-core`** (8 ГБ ОЗУ) — не выбирайте 4-core
6. **Create codespace** → подождите 2-3 минуты

В браузере откроется редактор VS Code с терминалом внизу.

✅ Вы видите командную строку в терминале.

---

## 💻 Шаг 3  Ориентация в терминале

Терминал — это место, куда вы вводите команды. Просто копируйте и вставляйте то, что указано в руководстве.

| Команда | Что делает |
|---|---|
| `cd ~` | Вернуться в домашнюю папку |
| `cd ~/minecraft-server` | Перейти в папку сервера |
| `pwd` | Показать, где вы находитесь |
| `mkdir -p имя` | Создать папку |
| `ls` | Показать список файлов |
| `sudo` | Выполнить от имени администратора |

> 💡 **Золотое правило:** каждый шаг этого руководства указывает, из какой папки выполнять команду. Если сомневаетесь, введите `pwd`.

---

## ☕ Шаг 4  Установка Java 21 (LTS)

Minecraft написан на Java. Версия **21** рекомендована PaperMC. Это **LTS**-версия (долгосрочная поддержка): самая стабильная и дольше всего сопровождаемая. Более новые версии существуют, но не являются LTS.

📍 *Из любой папки.*

Сначала проверьте, установлена ли уже Java:

    java -version

🔵 Если видите `openjdk version "21.0.x"` → переходите к Шагу 5.

Иначе:

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ Команда показывает `openjdk version "21.0.x"`.

---

## 🐍 Шаг 5  Установка Python 3 и pip

Crafty Controller разработан на Python. Нам нужны Python 3 и `pip` (менеджер пакетов) для его установки и запуска.

📍 *Из домашней папки (`cd ~`).*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ Обе команды выводят номер версии без ошибок.

---

## 🧱 Шаг 6  Загрузка и настройка PaperMC

### Создание папки

📍 *Из домашней папки (`cd ~`).*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### Установка jq

`jq` читает ответы API PaperMC для автоматического получения последней стабильной сборки.

    sudo apt install jq -y

### Загрузка PaperMC

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 Если команда не сработает, используйте фиксированную сборку:
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` показывает `server.jar` в списке.

### Принятие EULA

> ⚠️ **Юридическое обязательство.** Mojang требует принять лицензионное соглашение конечного пользователя (EULA) перед любым запуском. Без этого файла сервер откажется запускаться. Выполнив команду ниже, вы принимаете условия на [aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA).

    echo "eula=true" > eula.txt

✅ `ls` показывает `eula.txt` рядом с `server.jar`.

### Первый тестовый запуск

    java -Xms2G -Xmx4G -jar server.jar --nogui

Дождитесь сообщения `Done!` (1-2 мин), затем остановите:

    stop

✅ Сервер корректно останавливается, и вы возвращаетесь к командной строке.

### Создание скрипта запуска

Эти параметры называются *Aikar's flags*. Признанные сообществом оптимизации памяти, значительно снижающие лаги.

📍 *Вернитесь в домашнюю папку (`cd ~`).*

    nano start.sh

Вставьте:

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

Сохраните: **Ctrl+X** → **Y** → **Enter**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` показывает `-rwxr-xr-x` в начале строки.

---

## 📡 Шаг 7  Настройка Playit.gg

У вашего Codespace нет публичного IP-адреса. Playit.gg создаёт туннель и предоставляет адрес, который друзья вводят прямо в Minecraft. С вашей стороны настройка сети не требуется.

📍 *Из домашней папки (`cd ~`).*

### Установка агента

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### Привязка агента к учётной записи

    playit

В терминале появится ссылка для аутентификации. Откройте её в браузере → войдите → **Claim Agent**. Вернитесь в терминал → **Ctrl+C** → перезапустите в фоне:

    playit &

### Создание туннеля

1. На [playit.gg](https://playit.gg) → **Tunnels** → **Add Tunnel**
2. Заполните:
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MyServer`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 Отобразится публичный адрес (например, `myserver.playit.gg:12345`). **Запишите его. Его вы дадите друзьям.**

✅ Туннель отображается в панели со статусом "Connected".

---

## 🎛️ Шаг 8  Установка Crafty Controller

Crafty Controller — это панель веб-управления: запуск, остановка, просмотр логов, управление игроками через интерфейс, без командной строки.

📍 *Из домашней папки (`cd ~`).*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

Скрипт задаст несколько вопросов:

| Вопрос | Ответ |
|---|---|
| Порт | Нажмите **Enter** (останется `8443`) |
| Пользователь | `crafty` |
| Пароль администратора | Придумайте и **запишите** |
| Подтверждение | `y` |

Установка занимает 3-5 минут.

### Запуск Crafty

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### Обеспечение доступа к интерфейсу

1. VS Code → вкладка **PORTS** внизу
2. Если `8443` не отображается → **Add Port** → `8443` → подтвердите
3. Правый клик по `8443` → **Port Visibility** → **Public**
4. Откройте сгенерированный URL в новой вкладке
5. Предупреждение безопасности → **Дополнительно** → **Продолжить**
6. Войдите: `admin` + ваш пароль

✅ Вы на панели управления Crafty Controller.

---

## 🔗 Шаг 9  Добавление сервера в Crafty

**Servers** → **Create Server** → заполните:

| Поле | Значение |
|---|---|
| Server Name | `MyServer` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 При самом первом запуске Crafty может показать всплывающее окно для принятия EULA. Нажмите **I Accept** и перезапустите.

✅ Сервер переходит в статус "Running" (зелёный) в интерфейсе.

---

## ⏳ Шаг 10  Скрипт предотвращения сна

Codespace автоматически останавливается после 30 минут бездействия. Этот скрипт отправляет сигнал каждые 10 минут, чтобы сессия оставалась активной во время игры.

📍 *Из домашней папки (`cd ~`).*

    nano keep-alive.sh

Вставьте:

    #!/bin/bash
    # Keep-alive для GitHub Codespaces
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Enter**, затем:

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` предотвращает остановку скрипта при закрытии сессии. `&` запускает его в фоне.

✅ Через несколько минут `cat ~/keep-alive.log` покажет строки с метками времени.

---

## 💾 Шаг 11  Автоматические резервные копии

Этот скрипт каждый час создаёт сжатый архив вашего мира. В случае повреждения вы сможете восстановиться из недавней копии.

📍 *Из домашней папки (`cd ~`).*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

Вставьте:

    #!/bin/bash
    # Автоматическое резервное копирование мира Minecraft
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - Резервная копия создана." >> ~/backup.log

**Ctrl+X** → **Y** → **Enter**, затем:

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` показывает запланированную строку.

---

## 🟢 Запуск сессии

> 📌 При каждом открытии Codespace копируйте и вставляйте эти 4 команды в терминал в указанном порядке.

    # 1. Предотвращение сна
    nohup ~/keep-alive.sh &

    # 2. Туннель Playit.gg
    playit &

    # 3. Сервер Minecraft
    cd ~/minecraft-server && ~/start.sh &

    # 4. Интерфейс Crafty
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

Подождите 1-2 минуты → проверьте "Running" в Crafty → передайте адрес Playit.gg друзьям. 🎮

---

## 🔴 Остановка сессии

> ⚠️ **Закрыть вкладку недостаточно.** Codespace продолжает работать в фоне и потребляет квоту. Выполняйте эти шаги в конце каждой сессии.

**1. Остановить сервер Minecraft**

Через Crafty: нажмите кнопку ⏹️ в интерфейсе.

Через терминал:

    kill $(pgrep -f "server.jar")

**2. Остановить фоновые процессы**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Остановить Codespace** ← самый важный шаг

Через GitHub (рекомендуется):
1. [github.com/codespaces](https://github.com/codespaces)
2. Ваш активный Codespace (🟢 зелёный индикатор)
3. **`...`** → **Stop codespace**

Через редактор: слева внизу → имя Codespace → **Stop Current Codespace**

✅ Зелёный индикатор становится серым. Codespace остановлен.

---

## 🆘 Устранение неполадок

| Симптом | Решение |
|---|---|
| ❌ `java -version` не показывает `21.x` | Повторите Шаг 4 с начала |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `Permission denied` для `.sh` | `chmod +x имя_скрипта.sh` |
| ❌ Сервер не запускается (EULA) | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ Адрес Playit.gg не работает | `ps aux \| grep playit` → если нет, перезапустите: `playit &` |
| ❌ Crafty недоступен (порт 8443) | Вкладка **PORTS** → правый клик `8443` → **Port Visibility** → **Public** |
| ❌ Codespace останавливается посреди игры | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` и повторите загрузку |
| ❌ `OutOfMemoryError` в логах | Убедитесь, что машина **2-core / 8 GB RAM** |

По любым другим вопросам: скопируйте точное сообщение об ошибке на [Stack Overflow](https://stackoverflow.com) с тегом `[minecraft]` или `[github-codespaces]`. Сообщества: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 Контроль квоты

GitHub предоставляет **120 бесплатных ядро-часов в месяц**. На 2-ядерной машине каждый час игры расходует 2 → **60 реальных часов в месяц**.

Чтобы увидеть расход: **аватар GitHub** → **Settings** → **Billing & plans** → **Usage this month** → строка **Codespaces**

> ⚠️ Если вы приближаетесь к 120 ядро-часам, немедленно остановите Codespace и дождитесь ежемесячного обновления.

---

## 📎 Ресурсы

- [Документация PaperMC](https://docs.papermc.io)
- [Документация Crafty Controller](https://docs.craftycontrol.com)
- [Документация Playit.gg](https://playit.gg/support)
- [Документация GitHub Codespaces](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*Проверено на свежесозданном Codespace — май 2026.*
