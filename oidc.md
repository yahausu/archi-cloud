# OIDC
Ci dessous les différentes requêtes pour récupérer des tokens
## Login
```shell
curl --location --request POST 'http://localhost:8080/auth/realms/tindeer/protocol/openid-connect/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'username=toto' \
--data-urlencode 'password=toto' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'client_id=tindeer' \
--data-urlencode 'client_secret=a0f53195-8135-45af-b09c-954196a88ad0'
```

## Userinfo
```shell
curl --location --request GET 'http://localhost:8080/auth/realms/tindeer/protocol/openid-connect/userinfo' \
--header 'Authorization: Bearer XXXXXXXXX' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'username=toto' \
--data-urlencode 'password=toto' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'client_id=tindeer' \
--data-urlencode 'client_secret=a0f53195-8135-45af-b09c-954196a88ad0'
```

## Token info
```shell
curl --location --request POST 'http://localhost:8080/auth/realms/tindeer/protocol/openid-connect/token/introspect' \
--header 'Authorization: Bearer XXXXXXXX' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'client_id=tindeer' \
--data-urlencode 'client_secret=a0f53195-8135-45af-b09c-954196a88ad0' \
--data-urlencode 'token=XXXXXXXX'
```