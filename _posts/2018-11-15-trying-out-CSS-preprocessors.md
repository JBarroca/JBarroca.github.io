---
layout: post
title:  "Trying out CSS preprocessors"
date:   2018-11-15 12:20:00 +0100
categories: CSS preprocessors
---

using variables (particularly size and color varibles) is really helpful

applying functions such as the lighten() and darken() and passing varibles as their parameters  increases flexibility enormously.

using line comments (`//`) to see the effect of removing certain rules was a practical way in the beginning to make sure I understood certain rules and selectors

the use of partials makes it so much easier to grasp all the elements of what would have been a huge single stylesheet in plain CSS.


#### header ####
+ removed the solid borders of the base theme
+ changed the header's color and typographic formatting
+ added logo image with usual link to homepage

#### main ####
+ removed padding between header, body and footer wrappers
+ added content_img_left and content_img_right rules to be able to insert floating images

### footer ###
+ applied color formatting in coherence with the changes done to the header
