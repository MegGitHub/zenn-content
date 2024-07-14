---
title: "JavaScriptファイルを単体で簡単に動かす方法！"
emoji: "🚀"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["javascript", "vscode", "nodejs"]
published: true
---

:::message
本記事の執筆者：Claude 3.5 Sonnetさん
本記事の編集者：Meg

間違いなどありましたら、コメントで教えて頂けると嬉しいです！
:::

こんにちは、Megです！
今回は、JavaScriptファイルを単体で動かす方法についてご紹介します。
個人でJavaScriptの勉強をされている方や、手軽にjsファイルの動作確認をしたい方にとって、とても便利な方法です。

ちなみに、JavaScript・TypeScriptベースのReactはフロントエンドエンジニアには必須のスキルで、案件も豊富です。
この機会にJavaScript・TypeScriptへの理解を深めてみてはいかがでしょうか？

## この記事で学べること

- JavaScriptやTypeScriptをHTML、jsx、tsxに埋め込まずに単体で動かす方法
- VS Codeの拡張機能「Code Runner」の使い方と便利さ

## 結論

**Node.js + VS Code + 拡張機能「Code Runner」**の組み合わせで、簡単に環境構築ができます！

## Step 1: Node.jsのインストール

まずは、JavaScriptやTypeScriptを動かすのに必要な「Node.js」をインストールしましょう。

2024年版の詳細なインストール方法については、別途記事を作成予定です。それまでは、公式サイトの最新情報をご確認ください。

インストールが完了したら、ターミナルで以下のコマンドを入力してみてください。バージョンが表示されれば成功です。

```bash
node -v
```

## Step 2: Visual Studio Codeのインストール

次に、エディタである Visual Studio Code（通称VS Code）をインストールします。

インストール方法は[こちらの記事](https://biotech-univ.com/2021visual-studio-codemac/)が参考になります。

## Step 3: Code Runnerのインストール

いよいよVS Codeの拡張機能「Code Runner」をインストールします。

VS Codeの左側にある拡張機能欄から検索してインストールするか、[こちらのリンク](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)から直接ダウンロードすることができます。

## Code Runnerの設定

Code Runnerのインストールが完了したら、少し設定を変更して使いやすい環境を整えましょう。

### 出力設定：console.logの結果をVS Code上で確認

console.logなどの結果をVS Code上で表示するために、ターミナルに出力されるように設定します。

1. VS Codeの設定を開く（Windowsは `Ctrl+,`、Macは `Cmd+,`）
2. 検索バーに「code-runner.runInTerminal」と入力
3. チェックボックスにチェック

これで、実行結果がVS Codeのターミナルに表示されるようになります。

### 言語設定：JavaScriptを実行できるようにする

次に、Code RunnerでJavaScriptを実行できるように言語を設定しましょう。

1. VS Codeの設定を開く
2. 検索バーに「code-runner.executorMap」と入力
3. 「settings.jsonで編集」をクリック
4. 以下のコードを追加してください：

```json
"code-runner.executorMap": {
    "javascript": "node",
}
```

これで設定完了です！JavaScriptファイルを単体で実行できるようになりました。

## トラブルシューティング

設定を行ったのに上手くいかない場合は、以下のトラブルシューティングをお試しください。

### Q.1 設定が反映されません。どうすればいいですか？

A.1 VS Codeを再起動してみてください。
VS Codeの拡張機能の設定は再起動後に反映されることが多いです。それでも反映されない場合は、PCそのものの再起動をお試しください。

### Q.2 Code Runnerの設定が表示されません。

A.2 少し時間を置いてから再度確認してみてください。
拡張機能をインストールした直後は設定が表示されないことがあります。しばらく待つと表示されるようになりますので、落ち着いて待ちましょう。

## まとめ

JavaScriptファイルを単体で動かす環境が整いました。これで、HTMLやJSXファイルを作成することなく、手軽にJavaScriptの動作確認ができます。

JavaScriptを基にしたモダンな開発言語であるReactは、現在フロントエンド開発の主流となっており、案件も豊富です。
私自身も現在、ブログ構築にReactを使用しようと考えており、以下の書籍で学習中です。

**おすすめの書籍**

[モダンJavaScriptの基本から始める React実践の教科書 (最新ReactHooks対応) (Informatics&IDEA)](https://amzn.asia/d/07C7UKQ7)

以上で、JavaScriptファイルを単体で動かす方法の解説を終わります。この記事が皆さんのJavaScript学習の助けになれば幸いです。
何か質問があれば、コメント欄でお待ちしております！

## 参考文献

1. [VS CodeでJavaScriptを実行する方法](https://zenn.dev/kainari/articles/vscode-code-runner)
2. [Visual Studio Code 上で JavaScript を実行する](https://hinablo.hinasur.com/2020/05/16/visual-studio-code-%e4%b8%8a%e3%81%a7-javascript-%e3%82%92%e5%ae%9f%e8%a1%8c%e3%81%99%e3%82%8b/)
3. [VSCodeでJavaScriptを実行する方法](https://note.com/kushikushi_study/n/n55646d514748)
