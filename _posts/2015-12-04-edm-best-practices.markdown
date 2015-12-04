---
layout: post
title:  "Email Template Best Practices"
date:   2015-12-04
categories: best practices html git
---

### Rule #1. Design on a Width of 600 pixels
Emails are viewed in a variety of clients, and many different factors — advertisements, menus, and toolbars, just to name a few—can impact upon and minimize the view pane of the message.

The standard width for most emails is around 550-600 pixels, although the trend toward wider emails is increasing—and scalability, even on mobile devices, has improved with time. In short, if your design has to be wider than the 600 pixels, keep it under 700 pixels to be on the safe side.


### Rule #2. Use Background Images Sparingly

Since version 2007, Outlook has provided zero background image support. When using layered images in your design, be sure they can degrade gracefully. Always use a solid background color as a fallback for Outlook and make sure no crucial information or imagery exists solely in a background image.

![background images support](/images/css-background.jpg)

[See all CSS3 style that are support in different email clients](https://www.campaignmonitor.com/css/)


### Rule #3. Stick with System Fonts
Web fonts are not widely supported in email, so in most cases you’ll need a fallback. To circumvent the general lack of support available for handling these issues, stick with web-safe fonts like Arial, Helvetica, Tahoma, Times Roman, and Georgia.


### Rule #4. Strive for a Good Balance of Text-to-Image Ratio
At first, it might seem that the best way to preserve the design of an email is to throw it all in an image tag or slice it up into lots of images. Then there’s no need to worry about being limited to ugly system fonts or stripping of the background images, right?

Not quite. An image-heavy email will increase the chances of your email client flagging it as spam, resulting in damage to your sender reputation.

As a general rule, the best way to avoid ending up in the dreaded Spam folder is to make sure that your emails reflect a balanced image to text ratio.

Most email clients block images by default. With this in mind, incorporate text that summarizes the main point of your message: the offer, the announcement, the transaction taking place, the action for the consumer to take, etc. Some text — especially the main call to action — should be viewable upon opening the email, even if the images are shut off.

### Rule #5. Consider a Mobile-First Design
It’s true, CSS support in email has come a long way, and we can now incorporate some media queries to allow for responsive layouts — but by no means can we expect all clients and devices to support this yet.

It’s still wise to begin with a mobile-first design for optimal viewing across all platforms. Use single-column layouts, larger fonts, and clear and concise messaging and calls-to-action as much as possible.

Multi-column layouts don’t have to be off-limits for mobile, but keep them to a minimum as needed—and try to avoid going above a three-column layout.

### Rule #6: White Screen of Death
![Alt text with colour text](/images/white-text.jpg)
Avoid use white text for Alt text, user will not be able to see any text if images is block by the email client.

### Rule #7. Use a readable font
Use a minimum of 13 pixels (iPhone’s minimum font size), as smaller fonts get scaled up by the device and can affect your layout.

Watch out for bold, capitalized words. They're harder to read in smaller font on smaller screens, especially when they’re white-on-black, as in Sephora’s calls-to-action above.

High contrast font colours is always recommended for Web, but all the more important on mobile devices which are not only tiny, but often used in lower-light conditions

### Rule #8: Use alternate text for important images
This is especially important for headlines, special offers and other calls to action. Adds alternate text to the most important CTAs, and leaves blank images that are not so important. This is a great idea, it’s less cluttered and readers will be drawn right to the offers.

### Eye-catching Call to Action
![Eye-catching Call to Action](/images/internal_img2.jpg)

Calls to action (CTAs) are usually the most important part of a marketing email. They should be eye-catching, well-placed and above all, usable. The criteria for a great CTA are different depending on whether it is to be selected by a cursor or a finger. This is a powerful function of responsive email; to provide users on smaller touch-screen devices with finger-friendly buttons that are not affected by image blockers.

##  Responsive Email Design
Responsive email identifies a device’s screen or display size using the @media query and serves the appropriate layout determined by the designer. The most common “breakpoint” is 480 pixels (iPhone specs), but any breakpoint can be set to target various screen sizes including tablets and phablets.

Unlike scalable design which scales 100% table widths down to any screen size, responsive allows room for a designer to modify, hide, stack, add or expand/collapse content to optimize usability for narrow screens. While scalable design is certainly easier to code and is likely to “work” on all devices, usability can suffer when layout and design elements are not designed from the smallest screen up. Scalable’s best for text-based emails without many graphics (i.e. not retail email!) Responsive doesn’t require desktop layout to conform to narrow-width best practices, offering the most flexibility and control over merchandising and content.

Unfortunately, responsive isn’t foolproof. Some email clients like Gmail and Outlook strip out CSS style sheets and don’t support @media queries. It’s reported that users prefer to sync these accounts through a phone’s native email application (which does support @media) which will render the responsive version properly, but Gmail’s native app, for example, does not.

Best practice is to plan for failure by using flexible grid and fixed-width layout in your HTML template, and to test [known problematic clients](http://stylecampaign.com/blog/2012/10/responsive-email-support/).




