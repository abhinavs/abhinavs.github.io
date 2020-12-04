---
layout: post
title: Monorepo and Heroku
excerpt: "If you use a monorepo setup to power multiple apps, using Heroku isn't straight forward, however is easy and definitely possible."
tags: [Monorepo, Heroku]
comments: true
---

A monorepo is a repository that contains multiple sites or apps, each in its own subdirectory. Heroku assumes that you have different repos for different apps, however, in case you have a monorepo and want to deploy different apps on heroku to power them, you can do the following:

- Imagine you a widgets directory in your monorepo which you want to deploy on Heroku. Create a new app on Heroku dashboard for the app. Let’s call it `widgets-app-on-heroku`
- Set up APP_BASE config variable from Heroku dashboard with relative path from root to the directory app is served. In this case, it is served from a dist directory inside widgets directory. 
`APP_BASE=widgets/dist`
- Add Heroku [monorepo buildpack](https://github.com/lstoll/heroku-buildpack-monorepo) - specify the name of Heroku app here:
```
$ heroku buildpacks:add -a widgets-app-on-heroku 
 https://github.com/lstoll/heroku-buildpack-monorepo
``` 
- You probably would need to add more buildpacks depending upon your app stack, ensure that monorepo build pack is the first one in order. You can manage that from Heroku dashboard or add `-i 1` when you add monorepo buildpack
```
$ heroku buildpacks:add -i 1 -a widgets-app-on-heroku 
 https://github.com/lstoll/heroku-buildpack-monorepo 
```
I am using a static buildpack in this example
```
$ heroku buildpacks:set -a widgets-app-on-heroku 
 https://github.com/heroku/heroku-buildpack-static.git
```
- Add a new git Heroku remote for each app
```
$ heroku git:remote -a widgets-app-on-heroku
```
- Heroku names remote as heroku, rename the remote so that you can deploy each of your apps separately
```
$ git remote rename heroku heroku-widgets
```
- Now to deploy your app, you just need to push your main/master branch to this remote.
```
$ git push heroku-widgets master
```
- And done.
