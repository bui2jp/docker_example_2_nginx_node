## 秘密鍵の作成
```
openssl genrsa -out server.key 2048
```

## CSR（証明書署名要求）の作成
```
openssl req -new -key server.key -out server.csr
```

## CRT（SSLサーバ証明書）の作成
```
openssl x509 -days 3650 -req -signkey server.key -in server.csr -out server.crt
```