# data4good - season 13 - sufficiencylab

(tested in wsl)
prepare mattermost folder:  
```
mkdir -p ./volumes/app/mattermost/{config,data,logs,plugins,client/plugins,bleve-indexes}
sudo chown -R 2000:2000 ./volumes/app/mattermost
```

docker compose for all services.  
run with:  
` docker compose -f 'docker_compose.yml' up `

default url are:chmo
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