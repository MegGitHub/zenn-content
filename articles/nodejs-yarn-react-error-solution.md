---
title: "Node.jsとyarnでのReactアプリ開発中に発生したエラーの解決方法"
emoji: "🧵"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["react", "nodejs", "npm", "yarn"]
published: True
---
:::message
本記事の執筆者：ChatGPTさん
本記事の編集者：Meg

素のMegの記事が読みたい方はこちら！→[Meg Log](https://biotech-univ.com/)
:::

Reactアプリを開発するために、Node.jsとyarnを使用して環境構築を行っていましたが、`yarn start`実行時に以下のエラーが発生しました。このブログでは、エラーの解決方法をステップバイステップで紹介します。
それじゃいってみよう！

# エラー内容
トグル内に詳細なエラーを記載します。
:::details エラーメッセージ
/Users/user/GitHub/book-react-code/4/react-basic/node_modules/react-scripts/scripts/start.js:19
  throw err;
  ^

Error: error:0308010C:digital envelope routines::unsupported
    at new Hash (node:internal/crypto/hash:79:19)
    at Object.createHash (node:crypto:139:10)
    at module.exports (/Users/user/GitHub/book-react-code/4/react-basic/node_modules/webpack/lib/util/createHash.js:135:53)
    at NormalModule._initBuildHash (/Users/user/GitHub/book-react-code/4/react-basic/node_modules/webpack/lib/NormalModule.js:417:16)
    at /Users/user/GitHub/book-react-code/4/react-basic/node_modules/webpack/lib/NormalModule.js:452:10
    at /Users/user/GitHub/book-react-code/4/react-basic/node_modules/webpack/lib/NormalModule.js:323:13
    at /Users/user/GitHub/book-react-code/4/react-basic/node_modules/loader-runner/lib/LoaderRunner.js:367:11
    at /Users/user/GitHub/book-react-code/4/react-basic/node_modules/loader-runner/lib/LoaderRunner.js:233:18
    at context.callback (/Users/user/GitHub/book-react-code/4/react-basic/node_modules/loader-runner/lib/LoaderRunner.js:111:13)
    at /Users/user/GitHub/book-react-code/4/react-basic/node_modules/babel-loader/lib/index.js:59:103 {
  opensslErrorStack: [
    'error:03000086:digital envelope routines::initialization error',
    'error:0308010C:digital envelope routines::unsupported'
  ],
  library: 'digital envelope routines',
  reason: 'unsupported',
  code: 'ERR_OSSL_EVP_UNSUPPORTED'
}

Node.js v20.14.0
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
:::


# エラーの原因

このエラーは、Node.jsのバージョン20.14.0と一部の古いパッケージ（特にwebpack）が互換性の問題を抱えているために発生しているそう。この問題は、OpenSSLの変更が原因ぽい。

# 解決方法

## 環境変数を設定する

Node.js v17以上を使用している場合、環境変数を設定することで一時的にこの問題を回避できます。

1. プロジェクトのディレクトリで環境変数を設定して`yarn start`を実行します。

    ```sh
    export NODE_OPTIONS=--openssl-legacy-provider
    yarn start
    ```

これで、`yarn start`を再度実行すると、エラーが発生せずに開発サーバーが起動しました。

# まとめ

今回は、Node.jsのバージョン20.14.0で発生した`ERR_OSSL_EVP_UNSUPPORTED`エラーを解決する方法を紹介しました。私の場合、環境変数を設定する方法で問題を解決しました。
他にも、
1. Node.jsのバージョンを変更する方法
2. package.jsonのスクリプトを修正する方法
などもあるので、自分の環境に合った方法を選んで試してみてください。

本記事が、同じ問題に直面した方々の役に立てば幸いです！
