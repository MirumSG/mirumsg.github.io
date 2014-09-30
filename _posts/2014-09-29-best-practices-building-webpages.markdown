---
layout: post
title:  "Best Practices for Building Websites"
date:   2014-09-29
categories: best practices html
---

In order to keep our coding standards consistent, we've listed the best practices that we should follow when creating a website.

* [Folder Structure](#folderstructure)
* [Asset Optimization](#assetoptimization)
* [Using SVG](#usingsvg)
* [Animation and Transition](#animation)
* [Module Naming Convention](#modulenamingconvention)
* [Browser Compatibility](#browsercompatibility)

---

<a name="folderstructure" class="anchor" aria-hidden="true"></a>
##Folder Structure
Seperate Development from Build (For LIVE) folder
###Development Folder
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
###Build Folder
```
/css
/fonts
/images
/js
index.html
```

<a name="assetoptimization" class="anchor" aria-hidden="true"></a>
##Asset Optimization
* [Enable gzip compression.](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#text-compression-with-gzip)
* Remember to minify css & uglify js when website is ready to go live.
* Alternatively, we can also use source maps on minified CSS.
* [Ensure that images are optimized for web.](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization)

<a name="usingsvg" class="anchor" aria-hidden="true"></a>
##Using SVG for icons
* Replace simple icons with unicode.
* Replace complex icons with SVG.
* [Do not use icon fonts.](https://developers.google.com/web/fundamentals/media/images/use-icons?hl=en#use-icon-fonts-with-caution)

<a name="animation" class="anchor" aria-hidden="true"></a>
##Animation
* Keep animations to `opacity` or `transform`.
* Use CSS to handle animation with JS fallback.

<a name="modulenamingconvention" class="anchor" aria-hidden="true"></a>
##Cross-browser compatibility
* Use polyfill for IE.

<a name="browsercompatibility" class="anchor" aria-hidden="true"></a>
##Module-naming convention
* Format: module-name--submodule-name.

**For example:**

```
<div class="module-name">
  <div class="module-name--submodule-name">...</div>
</div>
```
* Keep naming to maximum 2 levels.

**For example:**

```
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
