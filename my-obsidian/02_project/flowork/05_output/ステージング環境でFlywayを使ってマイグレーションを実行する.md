  
## 前提  
---  
1. MosPの初期設定が完了していること  
2. Mavenが導入済みであること  
3. 操作ユーザに管理者権限があること  
4. 必要なツールがインストール済みであること  
   5. Git  
   6. Java 17  
   7. Maven  
   8. PostgreSQL  
9. 　マイグレーションファイルがあること  
  
※FlywayはMavenコマンドを初めて実行した時にMavenが自動的にFlywayをインストールされる（別途、手動でインストールする必要なし）。  
  
  
## 1.ベースラインを作成する  
---  
まずは基準点を作成する。  
MosPにはDDLファイルがすでに存在してます。  
そのファイルをFlywayの形式に合うように名前を変更したものがV5までのファイル。  
既存のDBにはV5までのファイル内容は適用済みのため、実行するとエラーになる。  
なので、V6以降のファイルのみ実行するよう設定するため、まずはベースラインの設定からおこなう。  
  
```  
# ベースライン作成  
mvn flyway:baseline -Dflyway.url=jdbc:postgresql://localhost:5432/mospv4 -Dflyway.user=usermosp -Dflyway.password=passmosp -Dflyway.baselineVersion=5 -Dflyway.baselineDescription="Production dump baseline"  
```  
  
  
  
## 2.マイグレーション状態を確認する  
---  
ベースラインが作成されたか下記コマンドで確認する。  
  
```  
# マイグレーション状態を確認  
mvn flyway:info \  
  -Dflyway.url=jdbc:postgresql://localhost:5432/mospv4 \  -Dflyway.user=usermosp \  -Dflyway.password=passmosp```  
  
  
V5がBASELINEとして設定されていることが確認できればOK。  
  
```angular2html  
[INFO] +-----------+---------+----------------------------+----------+---------------------+--------------------+----------+  
| Category  | Version | Description                | Type     | Installed On        | State              | Undoable |  
+-----------+---------+----------------------------+----------+---------------------+--------------------+----------+  
| Versioned | 0       | create user                | SQL      |                     | Below Baseline     | No       |  
| Versioned | 1       | create platform schema     | SQL      |                     | Below Baseline     | No       |  
| Versioned | 2       | create time schema         | SQL      |                     | Below Baseline     | No       |  
| Versioned | 3       | insert version info        | SQL      |                     | Below Baseline     | No       |  
| Versioned | 4       | grant platform permissions | SQL      |                     | Below Baseline     | No       |  
| Versioned | 5       | grant time permissions     | SQL      |                     | Ignored (Baseline) | No       |  
|           | 5       | Production dump baseline   | BASELINE | 2026-01-21 10:16:42 | Baseline           | No       |  
| Versioned | 6       | extend columns to 100      | SQL      |                     | Pending            | No       |  
+-----------+---------+----------------------------+----------+---------------------+--------------------+----------+  
```  
  
  
## 3.マイグレーションを実行する  
---  
マイグレーションを実行する。  
pom.xmlと同階層のディレクトリで実行しないとエラーになるため注意。  
  
```  
# マイグレーション実行  
mvn flyway:migrate -Dflyway.url=jdbc:postgresql://localhost:5432/mospv4 -Dflyway.user=usermosp -Dflyway.password=passmosp  
```  
  
  
## 4.マイグレーションが正常に実行できたか確認する  
---  
  
下記コマンドを実行して結果を確認する  
```  
mvn flyway:info  
```  
  
V6の「state」が「Success」になっていればOK  
```angular2html  
[INFO] +-----------+---------+----------------------------+----------+---------------------+--------------------+----------+  
| Category  | Version | Description                | Type     | Installed On        | State              | Undoable |  
+-----------+---------+----------------------------+----------+---------------------+--------------------+----------+  
| Versioned | 0       | create user                | SQL      |                     | Below Baseline     | No       |  
| Versioned | 1       | create platform schema     | SQL      |                     | Below Baseline     | No       |  
| Versioned | 2       | create time schema         | SQL      |                     | Below Baseline     | No       |  
| Versioned | 3       | insert version info        | SQL      |                     | Below Baseline     | No       |  
| Versioned | 4       | grant platform permissions | SQL      |                     | Below Baseline     | No       |  
| Versioned | 5       | grant time permissions     | SQL      |                     | Ignored (Baseline) | No       |  
|           | 5       | Production dump baseline   | BASELINE | 2026-01-21 10:16:42 | Baseline           | No       |  
| Versioned | 6       | extend columns to 100      | SQL      | 2026-01-21 10:32:00 | Success            | No       |  
+-----------+---------+----------------------------+----------+---------------------+--------------------+----------+  
```