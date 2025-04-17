# data4good - season 13 - sufficiencylab

## how to run-it

On a linux box or in wsl2 on windows,  
clone this repo,  
prepare mattermost folder:  
```
mkdir -p ./volumes/app/mattermost/{config,data,logs,plugins,client/plugins,bleve-indexes}
sudo chown -R 2000:2000 ./volumes/app/mattermost
```
docker compose run for all services: ` docker compose -f 'docker_compose.yml' up `

This will start all services.  

In keycloak, import the test realm: go to 'manage realms' > 'create realms' and import the file: realm-export.json
then go to 'Clients' > KCmattermost01 > 'credentials'  
and copy the client secret

In mattermost, create your admin account and in Console Settings, create yout OpenId config with the following values:
- discovery endpoint: http://keycloak:8080/realms/selfsuflab/.well-known/openid-configuration
- clientID: KCmattermost01
- client secret: paste it


default url are:
- keycloack: http://localhost:8080
- mattermost: http://localhost:8065
- kotaemon: http://localhost:7860
- moodle: https://localhost:8100

User admin created (for test/dev only !):
- keycloak : admin/admin
- kotaemon: admin/admin
- mattermost: none created at first start
- moodle: 

## TODO:
-[] check moodle install
-[] add a reverse proxy for subdomain


## REFS
- https://www.keycloak.org/getting-started/getting-started-docker
- https://github.com/Cinnamon/kotaemon
- https://docs.mattermost.com/deploy/server/deploy-containers.html
- https://moodledev.io/general/app/development/setup/docker-images


Keycloack + mattermost
- https://www.keycloak.org/securing-apps/oidc-layers
- https://docs.mattermost.com/onboard/sso-openidconnect.html