---
layout: post
title:  "XM Web Starter Kit"
date:   2014-09-16
categories: gulp javascript node.js handlebars scss
---

This static site generator is built with [Gulp.js](http://gulpjs.com/) running on top of [Node.js](http://nodejs.org/).

<img src="https://raw2.github.com/gulpjs/artwork/master/gulp-2x.png" width="80"><img src="http://saptarshichakraborty.me/blog3571/wp-content/uploads/2013/07/Nodejs_logo_light.png" width=200">
Gulp.js is what we call a JavaScript Task Runner. It helps you automate repetitive tasks such as minification, compilation, unit testing, linting, etc.

### Getting started

* Install Node.js<br/>
<http://nodejs.org/download/>

* Install gulp globally:

```js
$ npm install --global gulp
```

* Create your project folder

* [Download](https://github.com/XM-RichMedia/XM-Web-Boilerplate/archive/master.zip) or clone the boilerplate from [Github](https://github.com/XM-RichMedia/XM-Web-Boilerplate)<br/>
and copy the source files into your project folder.

* Install scss-lint plugin (Required for SCSS Linting):

```js
gem install scss-lint
```

* Install all dependency:

```js
$ npm install
```

* Run Gulp:

```js
$ gulp
```

---

### WINDOWS users take note:
Refer to the link on installation of Jekyll.<br>
<http://jekyll-windows.juthilo.com/5-running-jekyll/>

---

## Task integrated into the generator:

* [BrowserSync](#browsersync)
* [SASS](#sass)
* [SCSS Linting](#scss-linting)
* [JSHint](#jshint)
* [Handlebars](#handlebars)
* [Image Optimization](#image-optimization)
* [Autoprefixer](#autoprefixer)
* [Bourbon](#bourbon)
* [Neat](#neat)
* [EditorConfig](#editorconfig)

<br/><br/>
## BrowserSync

Why use BrowserSync?

When you’re making responsive websites, there’s a lot of tweaking and testing to do. BrowserSync makes your workflow faster by synchronising URLs, interactions and code changes across multiple devices. It’s wicked-fast and totally free.

Read here for more information:<br/><http://www.browsersync.io/>

---

## SASS

<img src="http://sass-lang.com/assets/img/logos/logo-235e394c.png" width="150">

Sass is the most mature, stable, and powerful professional grade CSS extension language in the world.
All CSS must be written using SCSS pre-processor and following the below folder structure:


```
|-- scss/
|
|-- base/
|   |-- _config_global.scss
|   |-- _config_site.scss
|   |-- _functions.scss
|   |-- _state.scss
|
|-- mixin/
|   |-- _all.scss
|   |-- _baseline.scss
|   |-- _grid.scss
|   |-- _media.scss
|   |-- _rem.scss
|   |-- _triangle.scss
|
|-- module/
|   |-- ...                 # Here are all your modules styles
|
|-- partials/
|   |-- _base.scss
|   |-- _buttons.scss
|   |-- _forms.scss
|   |-- _helper.scss
|   |-- _links.scss
|   |-- _lists.scss
|   |-- _normalize.scss
|   |-- _tables.scss
|   |-- _typography.scss
|
|-- vendor/
|   |-- ...                 # Here are all your 3rd-party css libraries
|
|-- main.scss
|-- ie.scss
```

<http://sass-lang.com/>

---

## SCSS Linting

`scss-lint` is a tool to help keep your [SCSS](http://sass-lang.com) files
clean and readable. Please install this gem manually before running the site generator.

### Requirements

* Ruby 1.9.3+
* Sass 3.3.0+
* Files you wish to lint must be written in SCSS (not Sass) syntax

### Installation

```
gem install scss-lint
```

---

## JSHint
JSHint is a program that flags suspicious usage in programs written in JavaScript.<br/>
<http://www.jshint.com/docs/>

### JSHint settings:

```js
{
  "node": true,
  "browser": true,
  "esnext": true,
  "bitwise": true,
  "camelcase": true,
  "curly": true,
  "eqeqeq": true,
  "immed": true,
  "indent": 2,
  "newcap": true,
  "noarg": true,
  "quotmark": "single",
  "undef": true,
  "unused": "vars",
  "strict": true,
  "trailing": true,
  "smarttabs": true
}

```

---

## Handlebars

![Handlebars](http://docs.codenvy.com/wp-content/uploads/handlebars-logo.png)
Handlebars provides the power necessary to let you build semantic templates effectively with no frustration.
Handlebars template engine works like SSI(Server-side includes) but you and also add logic to it and render out static html.
<http://handlebarsjs.com/>

### Things that could be use as templates:

* header
* footer
* Navigations
* common components on the site

You can easily extract pieces of your body HTML, and put them into a partial, for example templates/layout/footer.html:

```
<footer>
    <a href="thebestpage.html">This is a great link to click on</a>
</footer>
```

This is how the default page would look like when using the page_footer partial that was mentioned above:

```
{{ "{{ > layout/header "}}}}

<!-- Your HTML here -->
<p>Welcome to XM Static generator!</p>

{{ "{{> layout/footer "}}}}
```

---

## Image Optimization

Minify PNG, JPEG, GIF and SVG images with imagemin<br/>
<https://github.com/sindresorhus/gulp-imagemin>

All PNG, JPEG, GIF and SVG assets will be optimise with this plugins to reduce the file sizes.

---

## Autoprefixer

With the help of Autoprefixer you will never have to write a single prefix again. Ever!
Generator functions are also a thing of the past. Start writing real CSS3.

changing from this:

```css
a {
  transition: transform 1s
}
```

to this:

```css
a {
  -webkit-transition: -webkit-transform 1s;
  transition: -ms-transform 1s;
  transition: transform 1s
}
```

<https://github.com/metrime/gulp-autoprefixer>

---

## Bourbon

![Bourbon](http://bourbon.io/images/shared/bourbon-logo.png)
A simple and lightweight mixin library for Sass.
<http://bourbon.io/>

---

## Neat

![Neat](http://neat.bourbon.io/images/logotype.svg)
A lightweight semantic grid framework for Sass and Bourbon.
<http://neat.bourbon.io/>

---

## EditorConfig

![EditorConfig](http://editorconfig.org/logo.png)
EditorConfig helps developers define and maintain consistent coding styles between different editors and IDEs.
The EditorConfig project consists of a file format for defining coding styles and a collection of text editor plugins that enable editors to read the file format and adhere to defined styles. EditorConfig files are easily readable and they work nicely with version control systems.

```
# EditorConfig helps developers define and maintain consistent
# coding styles between different editors and IDEs
# editorconfig.org

root = true


[*]

# Change these settings to your own preference
indent_style = space
indent_size = 2

# We recommend you to keep these unchanged
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false
```

[Download plugin for your editor](http://editorconfig.org/#download)

***

<section>
  <h4>Built with these open source technologies:</h4>
  <div id="opensource-logo">
    <p>
      <a class="open-source__sass" href="http://sass-lang.com" title="Visit the Sass homepage"><span class="is-hidden">Sass</span></a>
      <a class="open-source__node" href="http://nodejs.org" title="Visit the NodeJS homepage"><span class="is-hidden">NodeJS</span></a>
      <a class="open-source__gulp" href="http://gulpjs.com" title="Visit the Gulp homepage"><span class="is-hidden">Gulp</span></a>
      <a class="open-source__handlebars" href="http://handlebarsjs.com" title="Visit the HandlebarsJS homepage"><span class="is-hidden">Handlebars</span></a>
    </p>
  </div>
</section>
