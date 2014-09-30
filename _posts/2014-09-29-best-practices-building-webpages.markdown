---
layout: post
title:  "Best Practices for Building Websites"
date:   2014-09-29
categories: best practices html
---

In order to keep our coding standards consistent, we've listed the best practices that we should follow when creating a website.

* [Asset Optimization](#assetoptimization)
* [Using SVG](#usingsvg)
* [Module Naming Convention](#modulenamingconvention)
* [Browser Compatibility](#browsercompatibility)

---
<a name="assetoptimization" class="anchor" aria-hidden="true"></a>
##Asset Optimization
* [enable gzip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#text-compression-with-gzip)
* minify css
* uglify js
* [ensure that images are optimized for web](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization)

<a name="usingsvg" class="anchor" aria-hidden="true"></a>
##Using SVG for icons
* Replace simple icons with unicode
* Replace complex icons with SVG
* [Do not use icon fonts](https://developers.google.com/web/fundamentals/media/images/use-icons?hl=en#use-icon-fonts-with-caution)

<a name="modulenamingconvention" class="anchor" aria-hidden="true"></a>
##Cross-browser compatibility
* use polyfill for IE

<a name="browsercompatibility" class="anchor" aria-hidden="true"></a>
##Module-naming convention
* Format module naming convention to: module-name--submodule-name

**For example:**

```
<div class="module-name">
  <div class="module-name--submodule-name">...</div>
</div>
```
* Keep naming to maximum 2 levels

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
