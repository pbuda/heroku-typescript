Typescript App on Heroku
========================

This is a simple Node.js + Express application written in Typescript
that can be built and run on Heroku.

## Deploy
To deploy this application simply create a new Heroku app

```
heroku create
```

and then just push the sources to Heroku

```
git push heroku master
```

Heroku will download all necessary libraries and fire the web
process defined in [Procfile](Procfile) that will build and start
the application.

## How this works

Typically you will add typescript as a devDependency to your package.json.
But this won't work on Heroku since those dependencies are not downloaded
(due to `NODE_ENV` being set to `production`).

In order to go around this issue you just simply need to add typescript
as a regular dependency and build the project after each push.
