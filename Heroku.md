$ npm install --save dotenv $ touch .env

//In .env
DATABASE_URL=postgres://localhost/databaseName

//In app.js
require('dotenv').load();  

//In knexfile.js
require('dotenv').load();

module.exports = {
  development: {
    client: 'postgresql',
    connection: process.env.DATABASE_URL,
    pool : {
      min: 2,
      max: 10
    }
  },
  production: {
    client: 'postgresql',
    connection: process.env.DATABASE_URL,
    pool : {
      min: 2,
      max: 10
    }
  }
};

//Then
$ createdb databaseName
$ knex migrate:latest --env production
$ knex seed:run --env production
$ heroku create siteName
$ heroku addons:create heroku-postgresql:hobby-dev
$ git add -A $ git commit -m "ready for heroku"
$ git push heroku master
$ heroku run knex migrate:latest
$ heroku run knex seed:run
$ heroku open

## For static files
https://github.com/heroku/heroku-buildpack-static
