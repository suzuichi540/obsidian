
## パターン１：スーパユーザーになりすます

```
sudo -u postgres psql
```

## パターン２：ネットワーク経由でログインする

```
psql -U postgres -h 127.0.0.1 -d postgres
```

パスワードを聞かれた場合、

```
postgres
```

を入力し、Enter。
すると、postgresに入れる。