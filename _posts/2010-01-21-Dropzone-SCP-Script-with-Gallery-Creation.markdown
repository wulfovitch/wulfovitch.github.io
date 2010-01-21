--- 
layout: post
title: "Dropzone SCP Script with Gallery Creation"
tags: 
- Dropzone
---

[Dropzone][dropzone] is a great tool for all your drag & drop needs on a OS X system. What is also cool about dropzone is, that you can extend it to your personal needs. I've always wanted a tiny little helper where I can drop my files onto. A gallery should automatically be created from these files and this gallery should be uploaded to my webspace afterwards. This kind of script would especially be useful if I wanted to show a friend some pictures rather quickly. I've never found a really good working solution for this on the web. At the end, I've created this dropzone script which does what I needed:

<p style="text-align: center">
<object width="480" height="385"><param name="movie" value="http://www.youtube.com/v/O5Njv9x6Glo&hl=de_DE&fs=1&"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/O5Njv9x6Glo&hl=de_DE&fs=1&" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="480" height="385"></embed></object>
</p>

This script takes care of a few things:

- If there is more than one file dropped onto the script, a gallery is created automatically.
- Big pictures are being resized to a reasonable size.
- Files which are not pictures are only getting linked to.
- You can enter a name for the gallery, if you are pressing the 'Control' key when dropping the files.
- After the upload, the url of the file or the gallery is pasted to the clipboard.

You need to have [ImageMagick][imagemagick] installed, if you want to get the resizing to work. The easiest way to install it, is via [MacPorts][macports] and the following terminal command: <code>sudo port install ImageMagick</code>. If you don't have ImageMagick installed, the pictures will be uploaded as is without resizing. 

You can obtain the script at [github] or [download it here][download].

[dropzone]: http://aptonic.com/ "Dropzone"
[imagemagick]: http://www.imagemagick.org "ImageMagick"
[macports]: http://www.macports.org/ "MacPorts"
[github]: http://github.com/wulfovitch/dropzone-user-scripts/blob/master/SCP%20Upload%20with%20Gallery.dropzone "Obtain the script at github"
[download]: /scripts/SCP-Gallery.zip "SCP Upload Script with Gallery"