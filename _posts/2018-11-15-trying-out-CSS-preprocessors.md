---
layout: post
title:  "Trying out CSS preprocessors"
date:   2018-11-15 12:20:00 +0100
categories: Sass
---

using variables (particularly size and color varibles) is really helpful

some syntactic elements such as nesting and `&` make it much simpler to read and write style rules. For example, using pseudo selectors and media-queries 

applying functions such as the lighten() and darken() and passing varibles as their parameters increases flexibility enormously.

using line comments (`//`) to see the effect of removing certain rules was a practical way in the beginning to make sure I understood certain rules and selectors

the use of partials makes it so much easier to grasp all the elements of what would have been a huge single stylesheet in plain CSS.

#### header ####
+ removed the solid borders of the base theme
+ used `@extends` to create a new header-specific wrapper class which inherited from the general wrapper class.
+ changed the header's color and typographic formatting
+ added logo image with usual link to homepage
+ used `<span>` elements and nested pseudo-selectors to change the color of the first letter of each word in the site title, as well as adding a media-query to decrease the title size and letter spacing on smaller screens

#### main ####
+ removed padding between header, body and footer wrappers
+ added content_img_left and content_img_right rules to be able to insert floating images
+ changed background colors, size and padding of the wrapper and added a box-shadow
+ changed the typographic formatting of post title elements
+ used pseudo-selectors to decorate posts' date metadata

#### footer ####
+ applied color formatting to both text and background in coherence with the changes done to the header