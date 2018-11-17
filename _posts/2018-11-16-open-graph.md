---
layout: post
title:  "Setting up Open Graph in a Jekyll website"
date:   2018-11-16 16:40:00 +0100
categories: Open Graph
---

Open Graph is a technology which allows you to control which elements and information are shown when someone shares a link to your page. This is done by defining meta tags in the `head` element of your HTML page. 

If we're using Jekyll to build a static website, the open graph meta tags are to be created in the `head.html` file typically located in the `_includes` folder. However, because of the many `{%raw%}{% if %}{%endraw%}`-blocks that will be needed in the code, it might be best to create a specific .html file for the open graph meta tags (for example, `_includes/open_graph.html`) and insert that via an `{%raw%}{% include %}{%endraw%}` into `_includes/head.html`.

### Basic metadata ###

The [Open Graph Protocol](http://ogp.me "The Open Graph Protocol") defines the following meta tags as the basic metadata:

+ `og:title`- The title of the object as it should appear within the graph;
+ `og:type`- The [type of the object](http://ogp.me/#types);
+ `og:image`- An image URL to represent our object within the graph (this property has other [optional structured properties](http://ogp.me/#structured));
+ `og:url`- The canonical URL of the object that will be used as the permanent ID in the graph.

Using Jekyll and Liquid's templating capabilities, we can use variables and `{%raw%}{% if %}{%endraw%}`-blocks to output the value of these meta tags. Here are some examples of that (adapted from [https://dev-notes.eu/2016/01/og-tags-for-jekyll/](https://dev-notes.eu/2016/01/og-tags-for-jekyll/)) which I have used on this website:

```
{%raw%}{% if page.title %}
    <meta property="og:title" content="{{ page.title }}">
{% else %}
    <meta property="og:title" content="{{ site.title }}">
{% endif %}

{% if page.title %}
    <meta property="og:type" content="article">
{% else %}
    <meta property="og:type" content="website">
{% endif %}

{% if page.featured-image %}
    <meta property="og:image" content="{{ site.url }}/{{ page.featured-image }}">
{% else %}
    <meta property="og:image" content="{{ site.url }}/assets/images/your-site-image.jpg">
{% endif %}

{% if page.url %}
    <meta property="og:url" content="{{ site.url }}{{ page.url }}">
{% endif %}{%endraw%}
```

### Optional metadata ###

Check [this link](http://ogp.me/#optional) to learn more about other possible meta tags.
