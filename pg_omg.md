#PG omg
  install via homebrew
    brew install postgresql
  idfk - setup database? if you've not used pg before?
    initdb /usr/local/var/postgres
  add user for your app (here sweet_spot)
    psql -d postgres
    create role sweet_spot SUPERUSER login createdb;
    =>CREATE ROLE
    postgres=# \q
  start the pg server
    pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
  stop pg: 
    pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log stop
  create the db
    rake db:create:all
  run migrations
    rake db:migrate
  enter pg console (for specified db): 
    psql database_name

  resources:
  - http://railscasts.com/episodes/342-migrating-to-postgresql?view=asciicast

Also, don't forget that in Heroku you can't drop and create your pg db, you have to use the 
heroku run rake pg:reset 
command