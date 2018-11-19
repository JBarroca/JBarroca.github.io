---
layout: post
title:  "Enter Static Site Generators!"
date:   2018-11-14 21:02:00 +0100
categories: Jekyll
---
This is my first time using a static site generator (SSG), Jekyll, so hooray! It's only my fourth ever website, so I can't really say this is disrupting that many routines (especially considering the first two of these websites were entirely done with Flash about 16 years ago).

So far, I've been delving into [Jekyll's documentation](https://jekyllrb.com/docs/ "Jekyll's Documentation") in order to understand the fundamentals, such as the structure of gem-based themes, how to use [Liquid](https://shopify.github.io/liquid/ "Liquid templating language") to introduce variables, logic and modularity and the use of CSS preprocessors within jekyll-built websites.

### Why SSGs? ###

The use of SSGs offers many possibilities. Here are a few examples:
+ Using layouts. A layout works as a template which wraps around the site's content. A singe html markup is defined as a starting point for the website's pages and other layouts can inherit from this template, adding changes as needed. Centralizing the structural information of many pages in a single .html file not only eliminates the tedious repetition of html code throughout multiple pages, but also decreases errors by allowing the developer to adjust the structure by editing a single html file, regardless how many different pages reference it.

+ Using `includes` to reference separate files for specific sections of the page. By defining specific sections as separate .html files and referencing them via `includes`, we are able to use Liquid's logic tags and filters to adapt the content of that section to the specific page the user is in. Thereby, it becomes possible, for example, to reference a single .html file for a navigation bar which can adapt its links to the page its currently in, or to only exhibit a header section on specific pages.

+ Version control of the site's content. By not requiring the use of a central database, which is usually separated from the code and its version control system, having instead the entire site's content stored as static files, it becomes possible to version control the entire site's content.

+ Better performance. Because an SSG-generated website consists entirely of static, ready-to-serve HTML files, no processing is needed on a site request. The website is therefore delivered much faster to the user.

+ Improved security. The lack of a central database and server-side functionality means there are fewer access points for intrusions.

### When to use SSGs? ###

SSGs are most useful for building sites more focused on delivering content than functionality. Most frequently, SSG websites are used for blogging, a perfect use for the way SSGs output content from text  data on Markdown or HTML files. Jekyll, for example, has inbuilt functionalities aimed specifically at blogging. Informational sites or documentation sites are also good use cases for SSGs. On the contrary, web applications or websites which require a lot of user interactivity such as discussion forums, user login or form filling, are not well suited for static websites. Although there are a few workarounds to add relative interactivity such as [Disqus commenting](https://disqus.com/ "Disqus"), they may increase the build complexity.

### My experience using an SSG ###

The first contact with an SSG was quite daunting because of everything I had to set up (even with the use of gem-based themes) and the time and reading it took me to understand the relationship between the various folders and the resulting static content after the site is built. However, after the initial contact, some advantages of using SSGs became immediately apparent. The possiblity to reuse and adapt html code via layouts and `includes` is a real productivity boost, especially when implementing changes to the markup after several pages have already been created.