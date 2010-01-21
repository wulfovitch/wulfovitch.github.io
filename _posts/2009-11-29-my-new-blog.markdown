--- 
layout: post
title: "My New Blog"
time: '23:12'
---

So, this is my new blog. In fact, my only blog before was a posterous account which I used as a blog[^1]. But posterous wasn't the blog engine I was looking for, so I finally decided to host the blog by myself. But what blog engine should I use? I could use [WordPress][wordpress] like everyone else does. There is nothing wrong with WordPress, but it doesn't fit my personal requirements. These requirements are:

* I don't want to use a blog system where I have to take care of updating the blog engine itself constantly. In most cases, this is the case, when a new security hole was discovered.
* I don't want to fiddle around with plugins or something like that to get something running.
* I want to write blog posts in [markdown][markdown]. 
* I want a blog engine, which doesn't need much resources.
* I want to have syntax highlighting for code snippets.
* I want to be able to backup my blog posts with no special effort.

Two months ago, I found out that I wasn't alone with these requirements. I stumbled upon [jekyll][jekyll], a static site generator written in ruby. "A static site generator? That sounds so like the 90s!" you may think. But in fact, a static site generator is the perfect system for a blog engine. Think about it, what makes a blog a blog? A blog consists of one or more blog entries, which are all consis of a title, a date and of the text of the blog entry itself. Nothing more. If you write only a few blog posts in a month, the content of the blog itself doesn't change very often. A perfect use case for a static site generator! Write the new blog post, generate the site, and upload this site with the tool you want. You don't even need a server with special capabilities! The server only needs to serve static html files. So you don't even have to worry about a special caching system, because caching is already given with static files! 

### Advantages of jekyll

With a generated static site, I don't have to worry about keeping the blog engine itself up to date. I don't have to fiddle around with plugins. With jekyll I can write blogposts in markdown. Syntax highlighting of code is also supported. Every single blog post is saved as a single text file, so I can easily back them up with my version control system of choice, which is [git][git] by the way. I don't have to worry about backing up the database. Because no database is needed at all!

### Final thoughts

I have now written more than I thought. Perhaps you want to comment to this blog post. This is the only thing, you can't support with a static site generator like jekyll. But what you can do, is to host the comments externally. For this purpose I use the [disqus commenting system][disqus], which I think is great, because they handle all the anti-spamming stuff for me. One thing more, I don't have to worry about. The less I have to worry about, the more I can be lazy. Which is a good thing, because all good programmers are programmers because they are lazy! ;) 

[wordpress]: http://wordpress.org "Wordpress blog engine"
[posterous]: http://posterous.com/ "posterous.com"
[jekyll]: http://github.com/mojombo/jekyll "Jekyll Static Site Generator"
[markdown]: http://daringfireball.net/projects/markdown/ "markdown markup language"
[git]: http://git-scm.com/ "git version control system"
[disqus]: http://disqus.com/ "Disqus commenting system"

[^1]: If you find it, you can keep it! :)