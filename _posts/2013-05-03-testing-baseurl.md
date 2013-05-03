---
layout: post
title: Testing Base URL
---
This is a test to see if I can find a way to test my site locally as well as 
have it work on GitHub pages as a project subdirectory and have the URLs 
screwed up.

What I've found is that the solution is to specify in `_config.yml` 
`baseurl: /projectname` and then in my code I use urls like:

<pre>
{% raw %}
&lt;a href="{{ site.baseurl }}{{ post.url }}" rel="bookmark"&gt;{{ post.title }}&lt;/a&gt;
and
&lt;link href="{{ site.baseurl }}/css/style.css" rel="stylesheet"&gt;
{% endraw %}
</pre>

This will make everything work properly when pushed to GitHub.  Now all that's 
left is making it work locally.

There are two solutions for this.  The first is to just run jekyll like normal 
and then go to `localhost:4000/projectname` and test your site.

If you'd prefer to not have that subdirectory locally while testing all you 
have to do is run `jekyll base-url=""` and then you can go to `localhost:4000`
and test like normal.

Just remember to remove the baseurl line if you decide to add a CNAME to your
site.