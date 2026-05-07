# 🟩 GitHub Codespacesで無料Minecraftサーバー

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4-62B47A?style=flat-square&logo=minecraft&logoColor=white)
![Java](https://img.shields.io/badge/Java-21_LTS-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PaperMC](https://img.shields.io/badge/PaperMC-1.21.4-0097D6?style=flat-square)
![Crafty](https://img.shields.io/badge/Crafty_Controller-4.x-7B2FBE?style=flat-square)
![Playit.gg](https://img.shields.io/badge/Playit.gg-tunnel-FF6B35?style=flat-square)
![Usage](https://img.shields.io/badge/usage-educational%20%2F%20private-lightgrey?style=flat-square)

> ⚠️ このガイドは教育および私的使用を目的としています。Codespacesでサーバーを24時間365日起動し続けることは、GitHubの利用規約に違反します。スリープ防止スクリプトは、60時間/月のクォータ内でゲームセッション*中*の切断を防ぐためだけのものです。さもないと、とあるGitが午前3時にあなたのドアをノックするでしょう...

---

## 📋 目次

- [何をするか](#-何をするか)
- [必要なもの](#-必要なもの)
- [ステップ0 - ツールを理解する](#-ステップ0--ツールを理解する)
- [ステップ1 - アカウントを作成する](#-ステップ1--アカウントを作成する)
- [ステップ2 - リポジトリとCodespaceを作成する](#-ステップ2--リポジトリとcodespaceを作成する)
- [ステップ3 - ターミナルに慣れる](#-ステップ3--ターミナルに慣れる)
- [ステップ4 - Java 21 LTSをインストールする](#-ステップ4--java-21-ltsをインストールする)
- [ステップ5 - Python 3とpipをインストールする](#-ステップ5--python-3とpipをインストールする)
- [ステップ6 - PaperMCをダウンロードして準備する](#-ステップ6--papermcをダウンロードして準備する)
- [ステップ7 - Playit.ggを設定する](#-ステップ7--playitggを設定する)
- [ステップ8 - Crafty Controllerをインストールする](#-ステップ8--crafty-controllerをインストールする)
- [ステップ9 - サーバーをCraftyに追加する](#-ステップ9--サーバーをcraftyに追加する)
- [ステップ10 - スリープ防止スクリプト](#-ステップ10--スリープ防止スクリプト)
- [ステップ11 - 自動バックアップ](#-ステップ11--自動バックアップ)
- [🟢 セッションを開始する](#-セッションを開始する)
- [🔴 セッションを停止する](#-セッションを停止する)
- [トラブルシューティング](#-トラブルシューティング)
- [クォータを監視する](#-クォータを監視する)

---

## 🎯 何をするか

GitHub Codespacesの無料クレジットを使ってMinecraftサーバーをクラウドで実行し、Webインターフェース（Crafty Controller）で管理し、Playit.ggのおかげでルーターを触らずにインターネット越しに友達がアクセスできるようにします。

事前知識は不要です。すべてのコマンドを説明します。

---

## 🧰 必要なもの

すべて無料です。

| | 項目 | 詳細 |
|---|---|---|
| 🌐 | Webブラウザ | Chrome, Firefox, Edge |
| 📧 | メールアドレス | 2つのアカウントを作成するため |
| 🐙 | GitHubアカウント | ステップ1で作成 |
| 🎮 | Playit.ggアカウント | ステップ1で作成 |
| ⏱️ | 約45分 | 初回インストール時 |

> 💡 一度セットアップすれば、新しいセッションのためにサーバーを再起動するのは3分もかかりません。

---

## 🔍 ステップ0  ツールを理解する

ここで5分読んでおくと、後々の混乱が大幅に減ります。

| ツール | 役割 |
|---|---|
| **GitHub Codespaces** | ブラウザからアクセスできるクラウド上のLinuxコンピュータ。無料枠では**120コア時間/月** → 2コアマシンなら**実質60時間のプレイ**が可能。 |
| **PaperMC** | サーバーエンジン。公式Mojangソフトウェアの改良版：よりスムーズ、ラグが少ない、プラグイン対応。 |
| **Playit.gg** | トンネル。GitHubはパブリックIPを提供しません。Playit.ggがアドレス（`myserver.playit.gg`）を作成し、友達が直接Minecraftに入力できます。 |
| **Crafty Controller** | Web管理パネル。クリックでサーバーを起動、停止、監視。 |

---

## 👤 ステップ1  アカウントを作成する

### 🐙 GitHub

1. [github.com/signup](https://github.com/signup) にアクセス
2. メール、パスワード、ユーザー名を入力
3. パズルを解く → **Create account**
4. メールで届いた6桁のコードを入力

✅ GitHubダッシュボードの右上に自分のユーザー名が表示されます。

### 🎮 Playit.gg

1. [playit.gg](https://playit.gg) にアクセス
2. **Login** → フォーム下部の **Sign up**
3. 項目を埋めて確認
4. メールで届いた確認リンクをクリック

✅ Playit.ggダッシュボードにアクセスできます。

---

## 🏗️ ステップ2  リポジトリとCodespaceを作成する

### リポジトリ

リポジトリはGitHub上のプロジェクトフォルダです。Codespaceを作成するためのベースになります。

1. GitHub上で：右上の **`+`** → **New repository**
2. 入力：
   - **Repository name:** `mc-server`
   - **Visibility:** `Private`
   - ☑️ **Add a README file**
3. **Create repository**

✅ `mc-server`リポジトリのページが表示されます。

### Codespace

> ⚠️ **重要なステップ** - マシンの選択がクォータを決定します。ここを間違えると半分になります。

1. **`Menu`** → **Codespaces** タブ
2. 右上の **New Codespace** をクリック
3. Minecraftサーバー用に作成したリポジトリを選択
4. 自分に最も近いリージョンを選択（あなたとサーバー間のpingが減少します）
5. **Machine type** → **`2-core`** (8 GB RAM) - 4-coreは選択しないでください
6. **Create codespace** → 2〜3分待つ

ブラウザでVS Codeエディタが開き、下部にターミナルが表示されます。

✅ ターミナルにコマンドプロンプトが表示されます。

---

## 💻 ステップ3  ターミナルに慣れる

ターミナルはコマンドを入力する場所です。ガイドの指示をそのままコピー＆ペーストしてください。

| コマンド | 動作 |
|---|---|
| `cd ~` | ホームフォルダに戻る |
| `cd ~/minecraft-server` | サーバーフォルダに移動 |
| `pwd` | 現在の場所を表示 |
| `mkdir -p 名前` | フォルダを作成 |
| `ls` | ファイル一覧表示 |
| `sudo` | 管理者として実行 |

> 💡 **黄金律：** このガイドの各ステップでは、どのフォルダからコマンドを実行するかが指定されています。迷ったら `pwd` と入力してください。

---

## ☕ ステップ4  Java 21 (LTS) をインストールする

MinecraftはJavaで書かれています。**21**はPaperMCが推奨するバージョンです。これは**LTS**（長期サポート）バージョンであり、最も安定し、最も長くメンテナンスされます。より新しいバージョンも存在しますが、LTSではありません。

📍 *任意のフォルダから。*

まず、Javaがすでに存在するか確認します：

    java -version

🔵 `openjdk version "21.0.x"` と表示されたら → ステップ5にスキップ。

そうでなければ：

    sudo apt update -y
    sudo apt install openjdk-21-jre-headless -y

    java -version

✅ コマンドが `openjdk version "21.0.x"` を表示します。

---

## 🐍 ステップ5  Python 3とpipをインストールする

Crafty ControllerはPythonで開発されています。インストールと実行にはPython 3と`pip`（パッケージマネージャ）が必要です。

📍 *ホームフォルダから (`cd ~`)。*

    sudo apt install python3 python3-pip -y

    python3 --version && pip3 --version

✅ 両方のコマンドがエラーなくバージョン番号を表示します。

---

## 🧱 ステップ6  PaperMCをダウンロードして準備する

### フォルダを作成

📍 *ホームフォルダから (`cd ~`)。*

    mkdir -p ~/minecraft-server
    cd ~/minecraft-server

### jqをインストール

`jq` はPaperMC APIの応答を読み取り、最新の安定ビルドを自動取得します。

    sudo apt install jq -y

### PaperMCをダウンロード

    wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]')/downloads/paper-1.21.4-$(curl -s https://api.papermc.io/v2/projects/paper/versions/1.21.4 | jq -r '.builds[-1]').jar

> 🔵 コマンドが失敗した場合、この固定ビルドを使用してください：
>     wget -O server.jar https://api.papermc.io/v2/projects/paper/versions/1.21.4/builds/196/downloads/paper-1.21.4-196.jar

✅ `ls` がリストに `server.jar` を表示します。

### EULAに同意する

> ⚠️ **法的義務。** Mojangはサーバー起動前にエンドユーザーライセンス契約（EULA）への同意を要求します。このファイルがないとサーバーは起動を拒否します。以下のコマンドを実行することで、[aka.ms/MinecraftEULA](https://aka.ms/MinecraftEULA) の条件に同意したことになります。

    echo "eula=true" > eula.txt

✅ `ls` で `eula.txt` が `server.jar` の隣に表示されます。

### 最初のテスト起動

    java -Xms2G -Xmx4G -jar server.jar --nogui

`Done!` メッセージを待ち（1〜2分）、その後停止します：

    stop

✅ サーバーが正常に停止し、コマンドプロンプトに戻ります。

### 起動スクリプトを作成

これらのパラメータは*Aikar's flags*と呼ばれ、ラグを大幅に削減するコミュニティ公認のメモリ最適化です。

📍 *ホームフォルダに戻ります (`cd ~`)。*

    nano start.sh

以下を貼り付け：

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

保存： **Ctrl+X** → **Y** → **Enter**

    chmod +x ~/start.sh

✅ `ls -l ~/start.sh` の行頭に `-rwxr-xr-x` と表示されます。

---

## 📡 ステップ7  Playit.ggを設定する

CodespaceにはパブリックIPがありません。Playit.ggがトンネルを作成し、友達が直接Minecraftに入力できるアドレスを提供します。ネットワーク設定は不要です。

📍 *ホームフォルダから (`cd ~`)。*

### エージェントをインストール

    curl -SsL https://playit-cloud.github.io/ppa/install.sh | bash

### エージェントをアカウントにリンク

    playit

ターミナルに認証リンクが表示されます。ブラウザで開く → ログイン → **Claim Agent**。ターミナルに戻る → **Ctrl+C** → バックグラウンドで再実行：

    playit &

### トンネルを作成

1. [playit.gg](https://playit.gg) で → **Tunnels** → **Add Tunnel**
2. 入力：
   - **Type:** `Minecraft Java (Game)`
   - **Name:** `MyServer`
   - **Local Port:** `25565`
3. **Add Tunnel**

📌 公開アドレスが表示されます（例：`myserver.playit.gg:12345`）。**メモしてください。これを友達に教えます。**

✅ ダッシュボードにトンネルが "Connected" ステータスで表示されます。

---

## 🎛️ ステップ8  Crafty Controllerをインストール

Crafty ControllerはWeb管理パネルです。起動、停止、ログ表示、プレイヤー管理をインターフェースから行い、コマンドラインは不要です。

📍 *ホームフォルダから (`cd ~`)。*

    git clone https://gitlab.com/crafty-controller/crafty-installer-4.0.git
    cd crafty-installer-4.0
    sudo ./install_crafty.sh

スクリプトがいくつか質問をします：

| 質問 | 回答 |
|---|---|
| Port | **Enter** を押す（`8443`のまま） |
| User | `crafty` |
| Admin password | パスワードを決めて**メモ** |
| Confirmation | `y` |

インストールには3〜5分かかります。

### Craftyを起動

    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py"

### インターフェースをアクセス可能にする

1. VS Code → 下部の **PORTS** タブ
2. `8443` が表示されない場合 → **Add Port** → `8443` → 確認
3. `8443` を右クリック → **Port Visibility** → **Public**
4. 生成されたURLを新しいタブで開く
5. セキュリティ警告 → **詳細設定** → **続行**
6. ログイン： `admin` + 設定したパスワード

✅ Crafty Controllerのダッシュボードが表示されます。

---

## 🔗 ステップ9  サーバーをCraftyに追加する

**Servers** → **Create Server** → 以下を入力：

| フィールド | 値 |
|---|---|
| Server Name | `MyServer` |
| Server Type | `Paper` |
| Server Jar | `server.jar` |
| Server Path | `/home/codespace/minecraft-server` |
| Max RAM | `4096` |
| Min RAM | `2048` |
| Server Port | `25565` |

**Create Server**

> 💡 初回起動時、CraftyがEULA同意のポップアップを表示する場合があります。**I Accept** をクリックしてから再起動してください。

✅ サーバーがインターフェースで "Running"（緑）ステータスになります。

---

## ⏳ ステップ10  スリープ防止スクリプト

Codespaceは無操作状態が30分続くと自動的に停止します。このスクリプトは10分ごとに信号を送り、プレイセッション中にセッションをアクティブに保ちます。

📍 *ホームフォルダから (`cd ~`)。*

    nano keep-alive.sh

貼り付け：

    #!/bin/bash
    # GitHub Codespaces用キープアライブ
    while true; do
        echo "$(date) - keep-alive ping" >> ~/keep-alive.log
        sleep 600
    done

**Ctrl+X** → **Y** → **Enter**、その後：

    chmod +x ~/keep-alive.sh
    nohup ~/keep-alive.sh &

`nohup` はセッションが閉じてもスクリプトが停止するのを防ぎます。`&` はバックグラウンド実行です。

✅ 数分後、`cat ~/keep-alive.log` にタイムスタンプ付きの行が表示されます。

---

## 💾 ステップ11  自動バックアップ

このスクリプトは1時間ごとにワールドの圧縮アーカイブを作成します。破損した場合、最近のバックアップに戻せます。

📍 *ホームフォルダから (`cd ~`)。*

    mkdir -p ~/minecraft-server-backups
    nano backup.sh

貼り付け：

    #!/bin/bash
    # Minecraftワールドの自動バックアップ
    tar -czf ~/minecraft-server-backups/world-$(date +%Y%m%d-%H%M%S).tar.gz \
      -C ~/minecraft-server world world_nether world_the_end
    echo "$(date) - バックアップ完了。" >> ~/backup.log

**Ctrl+X** → **Y** → **Enter**、その後：

    chmod +x ~/backup.sh
    (crontab -l 2>/dev/null; echo "0 * * * * /home/codespace/backup.sh") | crontab -

✅ `crontab -l` にスケジュールされた行が表示されます。

---

## 🟢 セッションを開始する

> 📌 Codespaceを開くたびに、この4つのコマンドをこの順序でターミナルにコピー＆ペーストします。

    # 1. スリープ防止
    nohup ~/keep-alive.sh &

    # 2. Playit.ggトンネル
    playit &

    # 3. Minecraftサーバー
    cd ~/minecraft-server && ~/start.sh &

    # 4. Craftyインターフェース
    sudo -u crafty bash -c "source /var/opt/minecraft/crafty/.venv/bin/activate && cd /var/opt/minecraft/crafty/crafty-4 && python3 main.py" &

1〜2分待つ → Craftyで "Running" を確認 → Playit.ggアドレスを友達に教える。🎮

---

## 🔴 セッションを停止する

> ⚠️ **タブを閉じるだけでは不十分です。** Codespaceはバックグラウンドで動作し続け、クォータを消費します。各セッションの終了時に以下の手順を実行してください。

**1. Minecraftサーバーを停止する**

Crafty経由：インターフェースの⏹️ボタンをクリック。

ターミナル経由：

    kill $(pgrep -f "server.jar")

**2. バックグラウンドプロセスを停止**

    pkill -f playit
    pkill -f keep-alive.sh
    pkill -f "python3 main.py"

**3. Codespaceを停止する** ← 最も重要なステップ

GitHubから（推奨）：
1. [github.com/codespaces](https://github.com/codespaces)
2. アクティブなCodespace（🟢 緑の点）
3. **`...`** → **Stop codespace**

エディタから：左下 → Codespace名 → **Stop Current Codespace**

✅ 緑の点が灰色に変わります。Codespaceは停止しました。

---

## 🆘 トラブルシューティング

| 症状 | 解決策 |
|---|---|
| ❌ `java -version` が `21.x` を表示しない | ステップ4を最初からやり直す |
| ❌ `pip3: command not found` | `sudo apt install python3-pip -y` |
| ❌ `.sh` で `Permission denied` | `chmod +x スクリプト名.sh` |
| ❌ サーバーが起動しない（EULA） | `echo "eula=true" > ~/minecraft-server/eula.txt` |
| ❌ Playit.ggアドレスが機能しない | `ps aux \| grep playit` → なければ再実行: `playit &` |
| ❌ Craftyにアクセスできない（ポート8443） | **PORTS** タブ → `8443` 右クリック → **Port Visibility** → **Public** |
| ❌ ゲーム中にCodespaceが停止する | `nohup ~/keep-alive.sh &` |
| ❌ `jq: command not found` | `sudo apt install jq -y` の後、ダウンロードを再試行 |
| ❌ ログに `OutOfMemoryError` | マシンが **2-core / 8 GB RAM** であることを確認 |

その他の問題：正確なエラーメッセージをコピーして [Stack Overflow](https://stackoverflow.com) に `[minecraft]` または `[github-codespaces]` タグで投稿。コミュニティ: [PaperMC Discord](https://discord.gg/papermc) · [Playit.gg Discord](https://discord.gg/playit-gg)

---

## 📊 クォータを監視する

GitHubは**月あたり120コア時間の無料枠**を提供します。2コアマシンの場合、プレイ1時間あたり2消費 → **月あたり実質60時間**。

使用量を確認するには：**GitHubアバター** → **Settings** → **Billing & plans** → **Usage this month** → **Codespaces** 行

> ⚠️ 120コア時間に近づいたら、すぐにCodespaceを停止し、月次リセットを待ってください。

---

## 📎 リソース

- [PaperMC ドキュメント](https://docs.papermc.io)
- [Crafty Controller ドキュメント](https://docs.craftycontrol.com)
- [Playit.gg ドキュメント](https://playit.gg/support)
- [GitHub Codespaces ドキュメント](https://docs.github.com/en/codespaces)
- [PaperMC Discord](https://discord.gg/papermc)
- [Playit.gg Discord](https://discord.gg/playit-gg)

---

*新規作成したCodespaceでテスト済み - 2026年5月*
