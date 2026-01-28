

## 前提
---

- ALBがあること
- ALBの変更権限があること


## ルールを追加する
---

ルールを追加する。

ルールの追加は以下の手順でおこなう。

- EC2にログインし、サイドバーのメニューから「ロードバランサー」を選択する
- メンテナンス画面を設定したいロードバランサーを選択する
- 選択したロードバランサーのメニューから「リスナーとルール」を選択する
- ポートを選択する
- ポートを選択するとポートの詳細ページが表示されるので、そのポートのルールを選択する
- リスナールールセクションの右上「ルールを追加する」を押す



![[ec2_mente.png]]



![[mente_ec2_2.png]]



## メンテナンスページを追加する
---

ここからはルールを追加する際、どのようにメンテナンスページを設定するかを解説する。


![[ec2_mente_3.png]]


※コード例

```
<!doctype html>
<html lang="ja">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Flowork 勤怠管理</title>
<style>html,body,p{margin:0;padding:0;line-height:1.3;}body{background-color:#fafafa; display:flex;align-items:center;justify-content:center;height:100svh;}div{border-radius:8px;padding:24px 48px;box-shadow:0 2px 2px #999;background-color:#fff;}.h{font-size:24px;text-align:center;font-weight:bold;}.t{font-size:20px;}a{font-weight:bold;color:#191969;}</style>
</head>
<body>
<div>
<p class="h">システムメンテナンス</p>
<p class="t"><br>2026年1月28日(水)15:00～16:00迄サービスを停止しております。
<br>打刻が必要な場合は、メンテナンス終了後に勤怠一覧画面から修正できます。<br>
<br>ご不便をおかけしますが、ご理解とご協力をお願いいたします。<br>
<br>Flowork 勤怠管理 開発担当</p>
</div>
</body>
</html>
```



## 反映を確認する
---

今回のメンテナンスページの表示条件は「URLのすべてのページ」なので、設定済みのドメインのどのページを叩いてもメンテナンスページが表示されるはず。


![[スクリーンショット 2026-01-28 12.53.58.png]]


問題なく表示ができていた！終わり！