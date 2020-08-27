# pro-academy-keycloak-postgres

run docker-compose up

admin console: http://localhost:8080/auth/

user/password: admin/Pa55w0rd

### Import Pro-academy client
import pro-academy client with imports/realm-export.json

add user. example: pafirstuser/pafirstpassword

regenerate secret 

obtain token with right secret and user credentials:
 
 curl -i -X POST \
                 -H "Content-Type:application/x-www-form-urlencoded" \
                 -d "client_id=pro-academy-client" \
                 -d "grant_type=password" \
                 -d "client_secret=6809a129-0910-4139-87fb-dd8a36628f73" \
                 -d "scope=openid" \
                 -d "username=pafirstuser" \
                 -d "password=pafirstpassword" \
               'http://localhost:8080/auth/realms/ProAcademy/protocol/openid-connect/token'