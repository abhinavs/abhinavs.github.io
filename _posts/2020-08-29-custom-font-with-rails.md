---
layout: post
title: Custom fonts in your Rails app
excerpt: "Using custom font in your rails app is simple, but not that straight forward"
tags: [Rails, Tech, TechNotes, Ruby, Font, Design, CSS]
comments: true
canonical_url: 'https://www.abhinav.co/custom-font-with-rails'
---
There are numerous free fonts available on the Internet, and most of them are also available on [Google Fonts](https://fonts.google.com/). Using fonts available on Google is an extremely simple and straight forward thing. You can use any of the following techniques

* Link it to them in your HTML file.

```html
 <link href="https://fonts.googleapis.com/css2?family=Roboto" rel="stylesheet">
```
* Import the font in your css file.

```css
@import url('https://fonts.googleapis.com/css2?family=Roboto');
```

However, there are times when fonts you want to use are not available on Google Fonts and other online font foundries - it may be because that particular font is not yet added there or it is a commerically licensed font. In those cases, you receive font files which can be in TrueType Format (`.ttf`), OpenType Format (`.otf`), Web Open Font Format (`.woff` or `.woff2`)

<br />

There can be more than one file for any particular font you are trying to use - they differ on font weight (normal, thin, medium, semibold, bold which are usually represented with numbers between 100 and 900) or font style (italic, normal etc.)

<br />

Here are sequence of steps you can follow to add these font files and corresponding css in your project:
<br />
* In your rails app, create a directory called fonts in `app/assets/` directory
* Copy all the font files in this directory
* In your `app/assets/stylesheets` directory, create a new file, let's call it fonts.css
* In fonts.css, add css explaining your fonts. Here is an example

```css
@font-face {
  font-family: "HK Grotesk";
  src: url("./HKGrotesk-Regular.woff2") format("woff2"),
    url("./HKGrotesk-Regular.woff") format("woff");
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "HK Grotesk";
  src: url("./HKGrotesk-ExtraBold.woff2") format("woff2"),
    url("./HKGrotesk-ExtraBold.woff") format("woff");
  font-weight: 800;
  font-style: normal;
}
```
* In application config (present in `config/application.rb`) add the following line in Application class

```ruby
class Application < Rails::Application
  # Precompile fonts.
  config.assets.paths << Rails.root.join('app/assets/fonts')
end
```
* And done; start using the new font by specifiying it in the font-family. In the above example, I am trying to use "HK Grotesk" font which is a good font, but still not available on Google font.

```css
font-family: 'HK Grotesk', sans-serif;
```

* Normally these steps should work, in case they don't, please also check your Content Security Policy (present in `config/initializers/content_security_policy.rb`)
