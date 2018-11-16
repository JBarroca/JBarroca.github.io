---
layout: post
title:  "humans.txt and robots.txt"
date:   2018-11-16 16:34:00 +0100
categories: misc
---

### humans.txt ###

Humans.txt is a simple `.txt` file containing relevant information about every person who has contributed to a website. The initiative comes from [humanstxt.org](http://humanstxt.org) and its goal is to define `humans.txt` as the standart way to present a website's authorship.

In my case, since I am developing this website as an individual project, I have no one else's information to present but my own. Therefore, in [this site's humans.txt file](/../../humans.txt), only my information is presented.

### robots.txt ###

[robots.txt](http://www.robotstxt.org), on the other hand, is used to regulate which [web robots](http://www.robotstxt.org/faq/what.html) can access our website, and what sections of our website they are allowed access to. Robots.txt also consists of a simple `.txt` file, which contains one or more sets of user-agent directives generally defined as:

```
User-agent: [user-agent name]
Disallow: [URL string not to be crawled]
(...)
```

Each directive defines a rule for the specified user-agent(s) and may contain multiple directives applying to that/those user-agent(s), be it `disallow` rules (restricting access by the user-agents to certain directories or files of our website), `allow` rules, `crawl-delay` rules (defining the amount of seconds a web robot has to wait before accessing the site's content) and `sitemap` rules, which indicate the location of any sitemaps associated with the site's URL.

For this website, I have simply defined a disallow rule restricting access to the images folder by Googlebot-Image (Google's image crawler):

```
User-agent: Googlebot-Image
Disallow: /assets/images/
```

