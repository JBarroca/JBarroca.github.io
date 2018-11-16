---
layout: post
title:  "Adding Disqus comments to a Jekyll website"
date:   2018-11-16 16:35:00 +0100
categories: Disqus
---

The process of adding Disqus comments to a Jekyll-built static website is not that complicated, but most sources of information (including the instructions on the Disqus website itself) tend to omit some basic directions that more seasoned users may find too obvious to earn mention, but which are vital for newcomers to these technologies such as myself. [This blog post](https://desiredpersona.com/disqus-comments-jekyll/) deserves to be mentioned, because it was almost perfect in this regard.

First, you need to go to [Disqus website](https://disqus.com/ "Disqus homepage") and create a free account (don't forget to open your email to verify your address). After creating an account, you can register your Jekyll website with Disqus by creating a Disqus shortname. You'll have to insert this shortname as a site variable in your Jekyll website, so copy it to your clipboard when you create it.

Open your Jekyll website's `_config.yml` file and create a site variable for the Disqus shortname you've just created:

```
disqus:
    shortname: your_site_shortname
```

> HINT: If you forgot your Disqus shortname like I did, go to Disqus website, click on your profile icon and go to 'Admin'. On the top-left corner of your Admin screen, you'll see a drop-down list of your websites. Click on the webiste whose shorname you're looking for and then check the website's URL, which will be `https://YOUR-SHORTNAME.disqus.com/admin`.

While you're looking at `_config.yml`, make sure that your site's URL variable is *not* an empty string. If you are implementing Disqus comments early on the development of your blog, you may have gotten this far without needing to edit this variable. Disqus comments, however, will require a global site URL (even if you haven't published it yet), so be sure to write something there.

```
URL: *something*
```

After you've edited _config.yml you can now proceed to create the include file for Disqus comments (typically `_includes/disqus_comments.html`). The code you need to paste in this file (the so-called Disqus Universal Embed Code) is provided to you by the Disqus website during the setup process, but you can paste the code below which will work on your Jekyll website via [Liquid variables](https://jekyllrb.com/docs/liquid/):


```
{% raw %}{% if page.comments != false %}
    <div id="disqus_thread"></div>
    <script>
    var disqus_config = function () {
        this.page.url = '{{ page.url | absolute_url }}';
        this.page.identifier = '{{ page.url | absolute_url }}';
    };

    (function() {
        var d = document, s = d.createElement('script');

        s.src = 'https://{{ site.disqus.shortname }}.disqus.com/embed.js';

        s.setAttribute('data-timestamp', +new Date());
        (d.head || d.body).appendChild(s);
    })();
    </script>
    <noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
{% endif %}{% endraw %}
```

Because of the surrouding `{% raw %}{% if %}{% endraw %}`-tag, all you have to do to disable comments on a specific post is to add `comments: false` to that post's YAML front-matter. You *don't* need to add that variable as true if you want comments on a post, they will be activated by default.

Now we need to add this .html via `{% raw %}{% include %}{% endraw %}` to our posts layout (typically `_layouts/post.html`). For that, all you need to do is add the following code after the closing `/article`tag:

```
{% raw %}{% if site.disqus.shortname %}
    {% include disqus_comments.html %}
{% endif %}{% endraw %}
```

And that's it! You can continue to add posts to your blog as usual and the Disqus comment section will appear at the bottom of each post. If you choose not to have comments on a specific post, just add `comments: false` in the front matter of that post's markdown file.