---
layout: post
title:  "Best Practices for Building Websites"
date:   2014-09-29
categories: best practices html
---

In order to keep our coding standards consistent, we've listed the best practices that we should follow when creating a website.

* [General Guidelines](#general-guidelines)
  * [Folder Structure](#general-folder-structure)
  * [Code Readability](#general-code-redability)
  * [Favicon](#general-favicon)
* [Assets](#assets)
  * [Icons](#assets-icons)
  * [Images](#assets-images)
* [Animation](#animation)
* [HTML](#html)
  * [Doctype](#html-doctype)
  * [Language](#html-language)
  * [Charset](#html-charset)
  * [Rendering Mode](#html-renderingmode)
  * [Module Naming Convention](#html-modulenamingconvention)
  * [Forms](#html-forms)
* [CSS](../css-scss-styleguide/)
* [JavaScript](../javascript-styleguide/)
* [Compatibility](#compatibility)
  * [Cross-Browser Compatibility](#compatibility-cross-browser)
  * [Responsive Sites](#compatibility-responsive-sites)
* [Performance](#performance)
  * [Asset Optimization](#performance-asset-optimization)
  * [Critical Rendering](#performance-critical-rendering)
* [Responsive Web Design Considerations](#responsive-web-design-considerations)

---

<a name="general-guidelines" class="anchor" aria-hidden="true"></a>
##General Guidelines

<a name="general-folder-structure" class="anchor" aria-hidden="true"></a>
###Folder Structure
Seperate Development from Build (For LIVE) folder
####Development Folder
```
/docs
/html
/src
  /fonts
  /images
  /includes
  /js
  /scss
  /templates
```
####Build Folder
```
/css
/fonts
/images
/js
index.html
```
<a name="general-code-redability" class="anchor" aria-hidden="true"></a>
###Code Readability
* Feel free to include comments to describe what each chunk of code does.
* Using whitespace to seperate chunk of codes is welcome.
* Compression of CSS and JavaScript files can be done either on server-side or during build.

<a name="general-favicon" class="anchor" aria-hidden="true"></a>
###Favicon
* [Favicon](http://css-tricks.com/favicon-quiz/) Requirements
* [Favicon Generator](http://realfavicongenerator.net/)

---

<a name="assets" class="anchor" aria-hidden="true"></a>
##Assets

<a name="assets-icons" class="anchor" aria-hidden="true"></a>
###Icons
* Replace simple icons with unicode.
* Replace complex icons with SVG.
* [Do not use icon fonts.](https://developers.google.com/web/fundamentals/media/images/use-icons?hl=en#use-icon-fonts-with-caution)

<a name="assets-images" class="anchor" aria-hidden="true"></a>
###Images
* All images should define ```alt``` text and ```title```.
* ```alt``` text should describe what the image is about, which will show in the event the image doesn't load.
* Image ```title``` should provide additional information in the form of a title.

For example:

```html
<img src="#" alt="Couples watching the sunset" title="Scenic view of Maya Bay">
```

---

<a name="animation" class="anchor" aria-hidden="true"></a>
##Animation
* Keep animations to `opacity` or `transform`.
* Use CSS to handle animation with JS fallback.

---

<a name="html" class="anchor" aria-hidden="true"></a>
##HTML

<a name="html-doctype" class="anchor" aria-hidden="true"></a>
###Doctype
* Use HTML5 doctype.

```html
<!doctype html>
```

<a name="html-language" class="anchor" aria-hidden="true"></a>
###Language
* Define language in html tag.

```html
<html class="no-js" lang="en">
```

<a name="html-charset" class="anchor" aria-hidden="true"></a>
###Charset
* Define charset.

```html
<meta charset="utf-8">
```

<a name="html-renderingmode" class="anchor" aria-hidden="true"></a>
###Rendering Mode
* Use X-UA-Compatible, IE=edge.

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```

<a name="html-modulenamingconvention" class="anchor" aria-hidden="true"></a>
###Module-naming convention
* Format: module-name--submodule-name.

**For example:**

```html
<div class="module-name">
  <div class="module-name--submodule-name">...</div>
</div>
```
* Keep naming to maximum 2 levels.

**For example:**

```html
<div class="module-name">
  <div class="module-name--submodule-name">
    <div class="header">...</div>
    <div class="text">...</div>
  </div>
  <div class="module-name--submodule-name-image">
    <img src="...">
  </div>
</div>
```

<a name="html-forms" class="anchor" aria-hidden="true"></a>
###Forms
* Use ```<label>``` to label fields and ```for``` attribute on the corresponding input field. This allows users to select the input field by clicking on the label as well.

```html
<label for="username">Name</label>
<input type="text" id="username" name="username" />
```

* All form elements MUST be enclosed within a ```<form>``` tag.
* All form elements MUST have a ```tabindex``` attribute defined.
* Use CSS to define the width of input fields instead of the ```size``` attribute.

For example:

```html
<input tabindex="1">
```

---

<a name="compatibility" class="anchor" aria-hidden="true"></a>
#Compatibility

<a name="compatibility-cross-browser" class="anchor" aria-hidden="true"></a>
##Cross-browser compatibility
* Use [modernizr](http://modernizr.com/docs/#load) to detect if HTML5 and CSS3 is supported by browser.
* Use polyfill for IE.

<a name="compatibility-responsive-sites" class="anchor" aria-hidden="true"></a>
##Responsive Sites
* Use [respond.js](https://github.com/scottjehl/Respond) to handle IE8 polyfill for min/max-width CSS3 media queries.

---

<a name="performance" class="anchor" aria-hidden="true"></a>
#Performance

<a name="performance-asset-optimization" class="anchor" aria-hidden="true"></a>
###Asset Optimization
* [Enable gzip compression.](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#text-compression-with-gzip)
* Remember to minify css & uglify js when website is ready to go live.
* Alternatively, we can also use source maps on minified CSS.
* [Ensure that images are optimized for web.](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization)

<a name="performance-critical-rendering" class="anchor" aria-hidden="true"></a>
##Site Performance
* Follow this guide on [Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/)

---

<a name="responsive-web-design-considerations" class="anchor" aria-hidden="true"></a>
#Responsive Web Design Considerations
* Advise against using '...' script-based ellipsis. It takes time to load, causes too much recalculations when the window size changes, and Flash of Unstyled Text (FOUT). If needed, use a gradient fade overlay to emulate "more content below" instead.
* Advise against revealing Call to Action (CTA) on hover. Touch devices don't have hover state and hence the CTA won't be obvious.
