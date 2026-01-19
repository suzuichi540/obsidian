
## 手順

### 1. V6ファイルを作成（user_idカラムの統一）

```
-- ユーザーIDの文字数を50文字から100文字に統一  
-- pfm_user.user_idは既に100文字だが、関連テーブルが50文字のままなので拡張  
  
-- pfa_user_extra_roleテーブル  
ALTER TABLE pfa_user_extra_role   
ALTER COLUMN user_id TYPE character varying(100);  
  
-- pfa_user_passwordテーブル  
ALTER TABLE pfa_user_password   
ALTER COLUMN user_id TYPE character varying(100);  
  
-- コメント  
COMMENT ON COLUMN pfa_user_extra_role.user_id IS 'ユーザーID（100文字に統一）';  
COMMENT ON COLUMN pfa_user_password.user_id IS 'ユーザーID（100文字に統一）';

```


### 2. V6マイグレーションを実行する
```
cd /Users/kojimaryoutarou/flowork  
mvn flyway:migrate
```


### 3. V6実行結果を　確認する

```
マイグレーション履歴
mvn flyway:info

user_idカラムの文字数確認
docker exec flowork-db psql -U postgres -d flowork -c "  
SELECT   
    table_name,   
    column_name,   
character_maximum_length FROM information_schema.columns WHERE column_name = 'user_id'   
  AND table_schema = 'public'  
ORDER BY table_name;  
"

```


実行結果

```
 flowork git:(feature/dev-12435_increase-character-limit) ✗ docker exec flowork-db psql -U postgres -d flowork -c "SELECT 
    table_name,
    column_name,
    character_maximum_length
FROM information_schema.columns
WHERE column_name = 'user_id'
  AND table_schema = 'public'
ORDER BY table_name;"
     table_name      | column_name | character_maximum_length 
---------------------+-------------+--------------------------
 pfa_user_extra_role | user_id     |                      100
 pfa_user_password   | user_id     |                      100
 pfm_user            | user_id     |                      100
(3 rows)


```


修正は無事完了！