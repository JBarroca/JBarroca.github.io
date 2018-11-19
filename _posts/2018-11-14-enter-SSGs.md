---
layout: post
title:  "Enter Static Site Generators!"
date:   2018-11-14 21:02:00 +0100
categories: Jekyll
---
This is my first time using a static site generator (SSG), [Jekyll](https://jekyllrb.com/). Hooray! It's only my fourth ever website, so I can't really say this is disrupting that many routines (especially considering the first two of these websites were entirely done with Flash about 16 years ago).

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

The first contact with this project was quite daunting. Docker, Jekyll, ruby gem-based themes, static websites, CSS preprocessors, Sass... all these different technologies to graps right from the beginning! It's no wonder the saying "Jekyll is for developers", because it takes a lot of effort just to be able to produce *something*.

I started by delving into [Jekyll's documentation](https://jekyllrb.com/docs/ "Jekyll's Documentation") in order to understand the fundamentals, such as the structure of gem-based themes, how to use [Liquid](https://shopify.github.io/liquid/ "Liquid templating language") to introduce variables, logic and modularity and the use of CSS preprocessors within jekyll-built websites. It took me a - relatively - long time just to understand the relationship between the various folders, layouts, assets, includes, etc. and the resulting static content after the website is built.

After the initial reading and the experimentation that followed (temptatively changing a front matter here, an include there and an html layout there), something clicked and I realised why static site generators can be a useful tool. The most striking improvement compared to my other recent projects with "traditional" HTML+CSS files was how much more modular all becomes by using layouts and includes. Goodbye, copy+pasting the same HTML elements all over different files and hello, immediate site-wide editing by changing just a single markup file. Then, the use of Liquid's if statements and for loops to build lists and navigation menus is really flexible. And finally, the possibility of adding pages and blog entries by simply creating new markdown text files is a breeze.

Since I'm only in the beginning of this journey, only time will tell how much I'll continue to use static site generators and this particular website here. Regardless, delving into all these different technologies was a very positive learning experience.