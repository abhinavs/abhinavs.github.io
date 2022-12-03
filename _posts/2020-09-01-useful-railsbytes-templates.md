---
layout: post
title: 8 useful Rails Bytes to improve your development process
excerpt: "Rails Bytes is a platform to share useful Ruby on Rails templates"
tags: [Ruby, RoR, Rails, Development, Tech, TechNotes, RailsBytes, HAML, DotEnv]
comments: true
canonical_url: 'https://www.abhinav.co/useful-railsbytes-templates'
---

[Rails Bytes](https://railsbytes.com/) is a platform created by Chris Oliver aka [excid3](http://excid3.com/) to share useful Ruby on Rails recipes/templates. These templates allow you to add features to both old and new apps. In the background, these templates may install a gem, run their installation steps, or edit configurations themselves. Of late, I have been using Rails Bytes for my new Rails apps, and here are a few of them (in no particular order) which I find very useful.

1. **HAML**: Add beautifully DRY, well-indented, clear markup.
<br />
I enjoy writing clean markup and I love [HAML](https://haml.info/) It also helps me understand the logic and intent clearly without getting lost in HTML. This template also lets you automatically convert your `.erb` files to `.haml` files. You also get an option to retain your `.erb` files in case you want to go back.
```sh
rails app:template LOCATION='https://railsbytes.com/script/x7msKK'
```
2. **Live Reload**: LiveReload with Webpack for views and viewcomponents.
<br />
I was recently exposed to Gatsby, and live reloading added so much to my productivity. Live Reload template tries to emulate the same for Rails. It used webpacker. There's [another template](https://railsbytes.com/public/templates/x7msEo) on Rails Bytes which achieves the same using guard.
```sh
rails app:template LOCATION='https://railsbytes.com/script/V1bs61'
```
3. **dotenv**: A Ruby gem to load environment variables from `.env`.
<br />
One of the tenets of a [twelve-factor app](http://12factor.net/) is storing  [configuration in the environment](http://12factor.net/config). In the development environment, this template uses [dotenv-rails](https://github.com/bkeepers/dotenv) gem which loads environment variables from .env file in the development environment.
```sh
rails app:template LOCATION='https://railsbytes.com/script/zOvsQ0'
```
4. **Simple form**: Rails forms made easy.
<br />
Rails default forms abstract native HTML forms well, [Simple form](https://github.com/heartcombo/simple_form) takes this abstraction a little further and helps you create forms easily.
```sh
rails app:template LOCATION='https://railsbytes.com/script/VQLslK'
```
5. **Recreate**: Rake task to drop schema and recreate the database.
<br />
I am not sure if it's only me - but because of multiple reasons, I tend to recreate my development database numerous times. Rake task added by this template makes it very easy to do.
```sh
rails app:template LOCATION='https://railsbytes.com/script/VQLsoK'
```
6. **Annotate**: Annotate Rails classes with schema and routes info.
<br />
Rails does magic with ActiveRecord, and while I completely love it, I also need to refer to column names very frequently. This template and [underlying](https://github.com/ctran/annotate_models) gem help you achieve that.
```sh
rails app:template LOCATION='https://railsbytes.com/script/Vqqsqg'
```
7. **Strong Versions**: Ensure your gems are appropriately versioned.
<br />
I have seen production issues arising because of version mismatch of gems and other external libraries. Install [strong_versions](https://github.com/bobf/strong_versions) gem to enforce stricter policy on your `Gemfile` requirements.
```sh
rails app:template LOCATION='https://railsbytes.com/script/xjNsMn'
```
8. **High Voltage**: Add High Voltage to manage static pages.
<br />
There are static pages in every app, and High Voltage using a good convention saves you from building unnecessary controllers for static pages. For more details check out [High Voltage](https://github.com/thoughtbot/high_voltage) gem.
```sh
rails app:template LOCATION='https://railsbytes.com/script/XbBsdZ'
```
