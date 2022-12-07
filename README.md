# easy-discourse

Discourse for local development/testing with docker-compose. This project is using Discourse 2.6.0.

## How to run
Do `docker-compose up`

The project will run on port 80, so visit `http://localhost`. I am using port 80 to avoid issues with assets that I didn't bother investigating.

All the changes are persistent; you can always see the codebase in the `data` folder.


## Account

Admin: http://localhost/admin


User: user

Password: bitnami123


## Installing a plugin

These are the steps I had to follow to install a plugin:

```bash
docker ps
docker exec -it <DISCOURSE IMAGE> /bin/bash
su discourse
cd /opt/bitnami/discourse/
RAILS_ENV=production bundle exec rake plugin:install repo=<PLUGIN_GIT_REPO>
RAILS_ENV=production bundle exec rake assets:precompile
RAILS_ENV=production bundle exec rake db:migrate
```
