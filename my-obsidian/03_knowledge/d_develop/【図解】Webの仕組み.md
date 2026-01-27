
## はじめに

新卒エンジニアが会社の研修で勉強した内容を図でまとめてみました。

## Webページのアクセスから表示までの流れ

[![Webの仕組み (9).png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2F8ed61fc5-457c-41a4-b795-c8ea3b1d9891.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=7691a01794b0df7678335fd61cb49299)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2F8ed61fc5-457c-41a4-b795-c8ea3b1d9891.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=7691a01794b0df7678335fd61cb49299)

## 解説

### 1. リクエスト開始とDNS解決のプロセス

[![Webの仕組み (8).png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2Fe983955d-4fb4-4a85-b2c5-9544e96c37ae.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=6bf795b1a2b413845943844737559978)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2Fe983955d-4fb4-4a85-b2c5-9544e96c37ae.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=6bf795b1a2b413845943844737559978)

**URLの入力:**  
ユーザーがブラウザにURL（例：[https://www.amazon.com](https://www.amazon.com/) ）を入力

**DNSキャッシュの確認:**

1. まずブラウザのローカルDNSキャッシュを確認
2. キャッシュにある場合はそのIPアドレスを使用
3. キャッシュにない場合は次のステップへ

**DNSサーバーへの問い合わせ:**

1. ブラウザはOSのDNSリゾルバに問い合わせ
2. さらにISPのDNSサーバーやルートDNSサーバーへと階層的に検索
3. 最終的に目的のドメイン名（www.amazon.com）に対応するIPアドレス（例：54.239.28.85）を取得

**IPアドレスの取得完了:**  
取得したIPアドレスを使ってWebサーバーへの接続準備完了

### 2. HTTPリクエスト・レスポンスの流れ

[![Webの仕組み (10).png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2F73c89fd0-1742-48cb-a3d3-5f6993e5c108.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=8f35d6cc698d37b43749c287fc6b5d96)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2F73c89fd0-1742-48cb-a3d3-5f6993e5c108.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=8f35d6cc698d37b43749c287fc6b5d96)

**TCP接続確立（3ウェイハンドシェイク）:**

1. クライアントがSYNパケットを送信
2. サーバーがACK+SYNパケットで応答
3. クライアントがACKパケットを送信して接続確立

**データ転送:**

1. クライアントがHTTPリクエストをサーバーに送信
2. サーバーがHTTPレスポンスをクライアントに返信

**コネクション切断（4ウェイハンドシェイク）:**

1. クライアントがFINパケットを送信
2. サーバーがACKパケットで応答
3. サーバーがFINパケットを送信
4. クライアントがACKパケットで応答して接続終了

### 3. サーバーサイドの処理

[![Webの仕組み (5).png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2Fc47fdd07-8079-478d-850a-182d820f480a.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=14ae8d52eb0a263e341ab31761a23c34)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2Fc47fdd07-8079-478d-850a-182d820f480a.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=14ae8d52eb0a263e341ab31761a23c34)

**リクエスト受付:**

1. Webサーバー（Apache、Nginxなど）がHTTPリクエストを受け取る
2. 静的コンテンツの場合はそのままファイルを提供

**動的コンテンツ生成:**

1. アプリケーションサーバーがプログラム（PHP、Ruby、Pythonなど）を実行
2. 必要に応じてデータベースからデータを取得・操作

**データベース処理:**

1. DBサーバーが接続管理、クエリ解析を行う
2. データの検索・更新・追加などの操作を実行
3. 結果をアプリケーションサーバーに返す

**レスポンス生成:**

1. 処理結果をHTMLなどの形式にまとめる
2. HTTPレスポンスヘッダーと共にクライアントへ送信

### 4. レスポンス生成と表示

[![Webの仕組み (7).png](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2F35922352-2167-4974-83fb-4d5836a32891.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a4c93a87cf99f3ca893c1eaa0dd0e954)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F4063100%2F35922352-2167-4974-83fb-4d5836a32891.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a4c93a87cf99f3ca893c1eaa0dd0e954)

**HTMLパース:**  
ブラウザがHTMLを受信し、DOM（Document Object Model）ツリーを構築

**CSSパース:**  
CSSを解析し、CSSOM（CSS Object Model）を構築  
スタイル情報をDOM要素に適用

**JavaScriptの実行:**  
JavaScriptコードを実行してDOMやCSSOMを操作

**レンダリングツリー構築:**  
DOMとCSSOMから実際に表示する要素のレンダリングツリーを作成

**レイアウト処理:**  
各要素の位置やサイズを計算

**ペイント処理:**  
色や画像などの視覚的要素を描画

**コンポジット:**  
複数のレイヤーを合成して最終的な画面を生成

**Webページ表示完了:**  
ユーザーに完成したWebページが表示される