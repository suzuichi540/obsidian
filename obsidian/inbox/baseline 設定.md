
### step1
バックアップ作成済み。
```
➜  flowork git:(feature/dev-12435_increase-character-limit) ✗ ls -lh ~/floworkmgmt_backup_*.sql
-rw-r--r--@ 1 kojimaryoutarou  staff   1.0M Jan 19 15:30 /Users/kojimaryoutarou/floworkmgmt_backup_20260119_153051.sql

```

### step2

現状は以下の通り。

```
 flowork git:(feature/dev-12435_increase-character-limit) ✗ docker exec flowork-db psql -U postgres -d floworkmgmt -c "\dt" | head -30
                      List of relations
 Schema |              Name               | Type  |  Owner   
--------+---------------------------------+-------+----------
 public | pfa_account                     | table | postgres
 public | pfa_address                     | table | postgres
 public | pfa_approval_route_unit         | table | postgres
 public | pfa_export_field                | table | postgres
 public | pfa_human_array                 | table | postgres
 public | pfa_human_binary_array          | table | postgres
 public | pfa_human_binary_history        | table | postgres
 public | pfa_human_binary_normal         | table | postgres
 public | pfa_human_concurrent            | table | postgres
 public | pfa_human_entrance              | table | postgres
 public | pfa_human_history               | table | postgres
 public | pfa_human_normal                | table | postgres
 public | pfa_human_retirement            | table | postgres
 public | pfa_human_suspension            | table | postgres
 public | pfa_import_field                | table | postgres
 public | pfa_phone                       | table | postgres
 public | pfa_user_extra_role             | table | postgres
 public | pfa_user_password               | table | postgres
 public | pfg_general                     | table | postgres
 public | pfm_app_property                | table | postgres
 public | pfm_approval_route              | table | postgres
 public | pfm_approval_unit               | table | postgres
 public | pfm_bank_base                   | table | postgres
 public | pfm_bank_branch                 | table | postgres
 public | pfm_db_version                  | table | postgres
 public | pfm_employment_contract         | table | postgres
 public | pfm_export                      | table | postgres

```

docker exec flowork-db psql -U postgres -d floworkmgmt -c "\dt" | head -30

```
flowork git:(feature/dev-12435_increase-character-limit) ✗ docker exec flowork-db psql -U postgres -d floworkmgmt -c "\d pfa_user_password"
                                 Table "public.pfa_user_password"
        Column        |            Type             | Collation | Nullable |        Default        
----------------------+-----------------------------+-----------+----------+-----------------------
 pfa_user_password_id | bigint                      |           | not null | 0
 user_id              | character varying(50)       |           | not null | ''::character varying
 change_date          | date                        |           | not null | 
 password             | character varying(50)       |           | not null | ''::character varying
 delete_flag          | integer                     |           | not null | 0
 insert_date          | timestamp without time zone |           | not null | 
 insert_user          | character varying(50)       |           | not null | ''::character varying
 update_date          | timestamp without time zone |           | not null | 
 update_user          | character varying(50)       |           | not null | ''::character varying
Indexes:
    "pfa_user_password_pkey" PRIMARY KEY, btree (pfa_user_password_id)
    "pfa_user_password_index1" btree (user_id)


```

### step3 
ベースラインは設定済み
