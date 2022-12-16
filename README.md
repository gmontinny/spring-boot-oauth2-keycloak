## docker-compose.yml
Substitua o ip do host interno pelo seu e execute o seguinte cmd para iniciar:

`docker-compose up --build`

Navegue até o seguinte url e, em seguida, faça o login keycloak com dev/123

`localhost:8080/api/consume/`

## Busque o token de acesso e atualize o token do servidor keycloak
Publique uma solicitação para obter um token de acesso:

`POST http://localhost:18080/auth/realms/spring-micro-main/protocol/openid-connect/token`  
 `Content-Type: application/x-www-form-urlencoded`
 
 `&client_id=spring-micro-gateway&username=dev&password=123&grant_type=password&client_secret=756b0558-018b-4809-b478-bd5b4995d325`

## Teste API
Get request com bearer token:

`GET localhost:8080/api/produce/`  
 `Authorization: Bearer <your bearer token here>`
