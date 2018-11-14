---
layout: post
title:  "First time with Static Site Generators"
date:   2018-11-14 21:02:00 +0100
categories: SSG
---
This is my first time using a static site generator (SSG), Jekyll, so hooray! It's only my fourth ever website, so I can't really say this is disrupting that many routines (especially considering the first two of these websites were entirely done with Flash about 16 years ago).

So far, I've been delving into [Jekyll's documentation](https://jekyllrb.com/docs/ "Jekyll's Documentation") in order to understand the fundamentals, such as the structure of gem-based themes, how to use [Liquid](https://shopify.github.io/liquid/ "Liquid templating language") to introduce variables, logic and modulatiry and the use of CSS preprocessors within jekyll-built websites.


#### Why SSGs? ####

The use of SSGs offers many possibilities: 
+ Using layouts. A layout works as a template which wraps around the site's content. A singe html markup is defined as a starting point for the website's pages and other layouts can inherit from this template, adding changes as needed. Centralizing the structural information of many pages in a single .html file not only eliminates the tedious repetition of the same html code throughout multiple pages, but also decreases errors by allowing the developer to adjust the structure by editing a single html file, regardless how many different pages reference it.

+ Using `includes` to reference separate files for specific sections of the page. By defining specific sections as separate .html files and referencing them via `includes`, we are able to use Liquid's logic tags and filters to adapt the content of that section to the specific page we're in. Thereby, it becomes possible, for example, to reference a single .html file for a navigation bar which can adapt its links to the page its currently in, or to only exhibit a header section on specific pages.

+ Version control of the site's content. By not requiring the use of a central database, which is usually separated from the code and its version control system, having instead the entire site's content stored as static files, it becomes possible to version control the entire site's content.

+ Better performance.

+ Improved safety.