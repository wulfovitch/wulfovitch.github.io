--- 
layout: post
title: "Change Terminal Colors on Remote Connections"
time: '10:57'
---

I often use ssh in order to work on remote servers. But often it is hard to tell at first sight, if a open terminal window displays the contents of remote connection or if it is a local one. Therefore it would be nice, if the terminal would automatically switch colors, when a remote connection is detected.  On [Stack Overflow][so] I found a solution for Terminal.app on OS X, which I adapted and improved a little bit:

{% highlight bash %}
#!/bin/sh
HOSTNAME=`echo $@ | sed s/.*@//`

# define background colors
BLACK_BG="{0, 0, 0, 50000}"
GREY_BG="{10000, 10000, 10000, 50000}"
RED_BG="{10000, 0, 0, 50000}"

# define font colors
GREEN="{0, 65535, 0}"
LIGHT_GREY="{55000, 55000, 55000}"


set_bg () {
  osascript -e
  "tell application \"Terminal\" to set background color of window 1 to $1
   tell application \"Terminal\" to set normal text color of window 1 to $2"
}

on_exit () {
  # set colors back to normal when quitting the remote connection
  set_bg "$BLACK_BG" "$GREEN"
}
trap on_exit EXIT

case $HOSTNAME in
  # you can set your production server in your .bash_profile file
  # like so: export production1="example.com"
  $production1|$production2|$production3) set_bg "$RED_BG" "$LIGHT_GREY";;
  *) set_bg "$GREY_BG" "$LIGHT_GREY" ;;
esac

/usr/bin/ssh "$@"
{% endhighlight %}

I've put this script into my <code>~/bin/</code> folder, which is the first place where my scripts are looked up. So don't forget to add this folder to your <code>$PATH</code>. Everytime a remote connection with ssh is started, this script is first called, changes the colors of the terminal and issues the real ssh command. 


[so]: http://stackoverflow.com/questions/157959/how-do-i-make-the-apple-terminal-window-auto-change-colour-scheme-when-i-ssh-to-a "Stack Overflow: How do I make the apple terminal window auto change colour scheme"