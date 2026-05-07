# ⛏️ 無料Minecraftサーバー - GitHub Codespaces

> **ゼロ円。インストール不要。面倒なし。**  
> クラウド上の高性能Minecraftサーバーを1時間以内に起動。

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/サーバー-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/パネル-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/トンネル-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![MITライセンス](https://img.shields.io/badge/ライセンス-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ 概要

このリポジトリは、GitHub Codespaces上で**完全無料**のMinecraftサーバーを構築するための**完全・段階的・検証済みガイド**です。

あなたと友達は、**1円も使わずに**、世界中どこからでもアクセスできる高性能サーバーで一緒にプレイできます（GitHubの無料枠内で）。

    Webブラウザ → GitHub Codespace (Linux) → PaperMC → Playit.gg → 友達 🎮

**得られるもの:**
- 🖥️ クラウド上の**Linux仮想マシン** (2コア, 8GB RAM, 32GBストレージ)
- 🟢 **PaperMC** - 最も最適化され安定したMinecraftサーバー
- 🧭 **Crafty Controller** - 数クリックでサーバーを管理するWebパネル
- 🌐 **Playit.gg** - ネットワーク設定不要で友達を招待できる公開トンネル
- 💾 **自動バックアップ**と**自動スリープ防止スクリプト**付き

---

## 🎯 対象者

**すべての人に。** このガイドは教育的で安心できるように書かれています。

| あなたのレベル | このガイドは適していますか？ |
|---|---|
| 完全な初心者、Linux未経験 | ✅ はい - すべて説明・理由付き |
| ターミナルに慣れている | ✅ はい - 要点だけ読めます |
| ネットワークや管理の経験なし | ✅ はい - Playit.ggが自動処理 |
| 予算なし | ✅ はい - 無料枠で100%無料 |

> **コピー＆ペースト**と**指示に従う**ことができれば、このサーバーを作れます。

---

## ⚡ 前提条件

必要なものは次のとおりです:

- [ ] **Webブラウザ** (Chrome, Firefox, Edge…)
- [ ] 無料の**GitHubアカウント** - [登録はこちら](https://github.com/signup)
- [ ] 無料の**Playit.ggアカウント** - [登録はこちら](https://playit.gg)

**自分のマシンにソフトウェアをインストールする必要はありません。**

---

## 📂 リポジトリファイル (近日公開)

⚠️ このセクションは現在作成中です。  
以下の情報はプレビューです。  
ガイドは [`Docs`](Docs) フォルダを参照してください。

| ファイル | 役割 |
|---|---|
| `README.md` | このファイル - プロジェクト概要 |
| `GUIDE.md` | 📘 **完全ガイド**、ステップバイステップ |
| `start.sh` | Aikar’s Flags最適化でサーバーを起動 |
| `keep-alive.sh` | Codespaceの自動スリープを防止 |
| `backup.sh` | Minecraftワールドの自動バックアップ |

---

## 🚀 クイックスタート (近日公開)

⚠️ このセクションは現在作成中です。  
以下の情報はプレビューです。  
ガイドは [`Docs`](Docs) フォルダを参照してください。

    # 1. このリポジトリをGitHub Codespaceにクローン
    # 2. Java 21をインストール
    sudo apt-get install -y openjdk-21-jdk

    # 3. サーバーを起動
    bash start.sh

    # 4. Playit.ggトンネルを起動 (別のターミナルで)
    ./playit

    # 5. ポート8443でCrafty Controllerを開く

> **詳細ガイドは [`JA_GUIDE.md`](Docs/JA_Guide.md) をご覧ください。**

---

## 🗂️ ガイドの内容

`JA_GUIDE.md` は以下の17ステップをカバーしています:

1. はじめに — 必要なもの
2. ツールの理解 (Codespaces, PaperMC, Crafty, Playit.gg)
3. GitHubとPlayit.ggアカウントの作成
4. リポジトリとCodespaceの作成
5. Linuxターミナルに慣れる
6. Java 21のインストール
7. Python 3とpipのインストール
8. PaperMCのダウンロードと設定
9. Playit.ggの設定
10. Crafty Controllerのインストール
11. Craftyにサーバーを追加
12. 自動スリープ防止スクリプト (keep‑alive)
13. 自動バックアップ
14. ✅ セッション開始チェックリスト
15. 🛑 セッション終了チェックリスト
16. トラブルシューティングとサポート
17. 月間クォータの監視

各ステップには「なぜ」の説明、コピーする正確なコマンド、動作確認が含まれています。

---

## ⚠️ 制限と責任ある使用

### 無料GitHub Codespacesクォータ

    120コア時間/月  →  2コアマシンで60時間のプレイ

| 行うこと | 避けること |
|---|---|
| ✅ セッション後にCodespaceを停止する | ❌ 24時間365日起動し続ける |
| ✅ Settings › Billing & plans を確認する | ❌ 使用量を無視する |
| ✅ 単発セッションに使う | ❌ 連続的な本番運用 |

> ⚠️ ゲームサーバーを常時稼働させることはGitHub Codespacesの利用規約に**準拠しません**。このガイドは時折の責任ある使用を前提としています。

### ストレージ
- 2コアマシンで**32GB**利用可能
- **バージョン管理されていない**データはCodespace削除時に失われます
- `backup.sh` を使用し、定期的にバックアップをコミットしてください

---

## 🤝 貢献

このガイドは慎重にメンテナンスされていますが、誤りが発生することがあります。誤字、古いコマンド、改善点を見つけましたか？

1. **問題を報告する [Issue](../../issues)** を作成してください
2. 修正を含む **[Pull Request](../../pulls)** を提案してください

---

## 💬 サポート＆コミュニティ

| リソース | 用途 |
|---|---|
| [PaperMC Discord](https://discord.gg/papermc) | Minecraftサーバーに関する質問 |
| [Playit.gg Discord](https://discord.gg/playit) | トンネル/ネットワークの問題 |
| [Stack Overflow](https://stackoverflow.com) | Linux/Javaエラー (`[minecraft]` `[github-codespaces]`) |
| [GitHub Issues](../../issues) | 本ガイド固有の問題 |

---

## 📄 ライセンス

**MITライセンス**の下で配布されています。著作権表示を保持する限り、自由に使用、変更、再配布できます。

---

<div align="center">

**プレイする準備はできましたか？**

### 👉 [完全ガイドを開く - JA_Guide.md](Tutorial/🇯🇵Ja_Guide.md)

*PaperMC、Crafty Controller、Playit.gg、GitHubの各コミュニティに感謝します。*

</div>
