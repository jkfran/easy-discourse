# easy-discourse

Discourse for local development/testing with docker-compose.


## Account

Admin: http://localhost/admin


User: user

Password: bitnami123


## Installing a plugin

```bash
docker ps
docker exec -it <DISCOURSE IMAGE> /bin/bash
cd /opt/bitnami/discourse/
RAILS_ENV=production bundle exec rake plugin:install repo=plugin_git_url
RAILS_ENV=production bundle exec rake assets:precompile
RAILS_ENV=production bundle exec rake db:migrate
```
