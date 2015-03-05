---
layout : post
title: Wordpress wp-content diretory and the Empty index.php file
comments: true
---

The Wp-Content directory stores everything for customizing wordpress.The diretory consists of themes,plugins,uploaded media and additional files to extend wordpress in any way imaginable.The wp-content directory and the sub-directories within it contain an index.php file.The contents of the file are

{% highlight php %}

<?php
//Silence is golden.

{% endhighlight %}

So,what's the point of this file ? Actually it is very important file. The index.php file blocks anyone from viewing a directory listing of the your wp-content folder.If the index.php file didn't existed and the web server allowed directory listings, then http:yoursite.com/wp-content/ would display all the files and folders in that directory.The implications of which you can understood yourself.So this file exists as a securtiy feature and should not be deleted for non-presence of content.
