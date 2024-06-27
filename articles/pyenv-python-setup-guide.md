---
title: "pyenvでラクラク環境構築！LinuxとMac OSユーザーのためのPython導入ガイド"
emoji: "🐍"
type: "tech"
topics: ["Python", "pyenv", "環境構築", "Linux", "MacOS"]
published: false
---

:::message

:::

Python環境の構築で頭を悩ませていませんか？今回は、pyenvを使って簡単にPython環境を整える方法をご紹介します。何番煎じだって感じだけど、環境構築する時毎回作り方忘れちゃうからしょうがない！

## この記事で学べること

- pyenvのインストール方法（思ったより簡単ですよ）
- pyenvでPythonをインストールする方法
- 仮想環境の作り方（プロジェクトをキレイに保つコツ）
- requirements.txtの使い方（依存関係管理の強い味方）

## 前提条件

- LinuxまたはMac OSを使っていること
- ターミナルの基本操作ができること

それでは、さっそく始めましょう！

## pyenvをインストールしよう

まずはpyenvをインストールします。思ったより簡単ですよ。

### 依存関係のインストール

pyenvを使うには、いくつかのパッケージが必要です。OSに応じて以下のコマンドを実行してください。

Linuxの場合（Ubuntu系）:

```bash
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev python-openssl git
```

Mac OSの場合:

```bash
brew install openssl readline sqlite3 xz zlib
```

### pyenvのインストール

次に、pyenv本体をインストールします。ワンライナーでできちゃいます。

```bash
curl https://pyenv.run | bash
```

インストールが終わったら、設定を追加しましょう。

Bashを使っている場合は`.bashrc`に、Zshを使っている場合は`.zshrc`に以下の行を追加してください：

```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc  # または ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc  # または ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc  # または ~/.zshrc
```

設定を反映させるために、新しいターミナルを開くか、次のコマンドを実行してください：

```bash
source ~/.bashrc  # または ~/.zshrc
```

これで準備完了です。簡単でしたね。

## Pythonをインストールしてみよう

pyenvを使えば、Pythonのインストールはとても簡単です。こんな感じでできます：

```bash
pyenv install 3.12.3
pyenv global 3.12.3
```

ちゃんとインストールできたか確認してみましょう：

```bash
python --version
```

`Python 3.12.3`と表示されたら成功です。お疲れさまでした！

## 仮想環境を作ろう

プロジェクトごとに環境を作ってみましょう。これができたら脱初心者感ある。

```bash
python -m venv myproject_env
source myproject_env/bin/activate
```

これで、プロジェクト専用の環境が作れました。仮想環境　is ただのディレクトリ。

## requirements.txtを使いこなそう

最後に、依存関係の管理方法をマスターしましょう。`requirements.txt`を使えば、環境の再現が簡単にできます。

必要なパッケージをインストールしたら、こんな感じでrequirements.txtを作れます：

```bash
pip freeze > requirements.txt
```

他の環境で同じ設定を再現したいときは、こうします：

```bash
pip install -r requirements.txt
```

これで環境の共有も楽チンですね。

## まとめ

いかがでしたか？pyenvを使えば、Python環境の構築がグッと簡単になります。
複数のプロジェクトを扱う方や、チームで開発する方には特におすすめです。

この記事で紹介した方法を使えば、効率的にPython環境を構築できるはずです。
ぜひ試してみてください。

俺はxxx & xxxの高みで待っている。