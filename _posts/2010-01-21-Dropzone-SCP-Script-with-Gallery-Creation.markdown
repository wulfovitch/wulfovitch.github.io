--- 
layout: post
title: "Dropzone SCP Script with Gallery Creation"
time: '21:34'
tags: 
- Dropzone
---

[Dropzone][dropzone] is a great tool for all your drag & drop needs on a OS X system. Also cool about dropzone is, that you can extend it to your personal needs. I've always wanted a tiny little helper where I can drop my files onto. A gallery should automatically be created from these files and this gallery should be uploaded to my webspace afterwards. This kind of script would especially be useful if I wanted to show a friend some pictures rather quickly. I've never found a really good working solution for this on the web. At the end, I've created this dropzone script which does what I needed:

<p style="text-align: center">
<object type="application/x-shockwave-flash" width="480" height="385" data="http://www.youtube.com/v/O5Njv9x6Glo"><param name="movie" value="http://www.youtube.com/v/O5Njv9x6Glo" /></object>
</p>

This script takes care of a few things:

- If there is more than one file dropped onto the script, a gallery is created automatically.
- Big pictures are being resized to a reasonable size.
- Files which are not pictures are only getting linked to.
- You can enter a name for the gallery, if you are pressing the 'Control' key when dropping the files.
- After the upload, the url of the file or the gallery is pasted to the clipboard.

You need to have [ImageMagick][imagemagick] installed, if you want to get the resizing to work. The easiest way to install it, is via [MacPorts][macports] and the following terminal command:

    sudo port install ImageMagick

If you don't have ImageMagick installed, the pictures will be uploaded as is without resizing. 

You can obtain the script at [github][github] or [download it here][download].

#### Update

The script resides now at the official [dropzone user scripts repository][user_scripts], too!  

[dropzone]: http://aptonic.com/ "Dropzone"
[imagemagick]: http://www.imagemagick.org "ImageMagick"
[macports]: http://www.macports.org/ "MacPorts"
[github]: http://github.com/aptonic/dropzone-user-scripts/blob?path%5B%5D=SCP+Upload+with+Gallery.dropzone&raw=true "Obtain the script at github"
[download]: /scripts/SCP-Gallery.zip "SCP Upload Script with Gallery"
[user_scripts]: http://github.com/aptonic/dropzone-user-scripts