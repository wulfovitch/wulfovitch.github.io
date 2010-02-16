--- 
layout: post
title: 'Jekylless'
time: '21:33'
tags: 
- Jekyll
---

[Tate Johnson][tatey] recently created his own fork of [Jekyll][jekyll] named [tatey-jekyll][tatey-jekyll]. He added the support for [LESS CSS][lesscss] and growl notifications to it. I liked the idea and merged the latest changes from Jekyll into his fork.

While I was at it, I also added the support for specifying the concrete time for a blog post in the yaml from matter. Whenever do you publish blog posts at twelve o'clock at night?

Tate liked the changes I made and we've agreed that we will continue to develope this fork under the name [Jekylless][jekylless]. The name Jekylless was chosen to show the projects' support for LESS CSS.

We both will integrate a few more features into this fork, but we've decided to stay as close as possible to the codebase of the original Jekyll, so that switching to our fork should be easy for every existing jekyll user.

For more information about Jekylless, checkout the [readme][jekylless] of the project on github or install the [Jekylless gem][gemcutter] directly. 

[tatey]: http://tatey.com
[tatey-jekyll]: http://tatey.com/2009/12/05/forking-jekyll-now-with-less-and-growl-notifications/
[jekyll]: http://github.com/mojombo/jekyll
[jekylless]: http://github.com/tatey/jekylless
[lesscss]: http://lesscss.org/
[gemcutter]: http://gemcutter.org/gems/jekylless