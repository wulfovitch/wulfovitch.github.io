--- 
layout: post
title: "About URL-Shorteners"
time: '21:33'
---

URL-Shorteners are getting popular these days, due twitter's 140 character limitation. But what happens behind the scenes, if you are opening a url, created by an url-shortener? The shortener takes the request from the browser, looks up the given value of the short url in the database and redirects the browser to the original site. And here is the point, where the trouble comes in:

* A short-url is not human-readable and therefore all semantic information is lost. You have no idea, to which url the short-url is leading you to and maybe you are being refered to a site you don't wanted to visit at all.
* If the url shortener service is shutdown or not reachable for some reason, you have no idea to what url the short-url was pointing to.
* In some cases, some url-shortening services redirected old short-urls to malware sites or something like that. If you or somebody is looking up some old tweet of you, the short-url has become useless although the original maybe still available.

Short-urls are adding a layer of indirection to the internet, which is not needed in my opinion.

### What could Twitter do about short-urls?

People are using url-shorteners, because they are forced to limit themselves to 140 characters. Twitter could implement a different counting mechanism:

* A url is counted as 20 characters no matter how long the url is in reality
* Limit the maximum number of urls in a tweet to 3.

By using this behaviour, no one has a real need for short-urls anymore and you will always know, how the real url looks. It should be fairly easy to implement this for twitter, but i think they are not doing this, because people cheat to get more characters in a single by simple typing something like: "http://and-i-also-wanted-to-say-this-and-that.com". In my opinion, this would be acceptable tradeoff if we could get rid of url-shorteners! You could just unfollow the people who are abusing the now legal long urls for something else and you are done.

### My current solution

Because I don't think twitter will solve the problem with url-shorteners in the near future, I have set up [my own][wulfi.net] with the help of Shaun Inman's [lessn][lessn]. This solution won't help to get rid of short-urls, but I am at least no longer dependent of a third party url shortener. I am in control of the short-urls I have posted on twitter and so I will never ever lose a link again, because a short url service abused my trust in their service.



[wulfi.net]: http://wulfi.net/ "wulfi.net"
[lessn]: http://www.shauninman.com/archive/2009/08/17/less_n "lessn"
