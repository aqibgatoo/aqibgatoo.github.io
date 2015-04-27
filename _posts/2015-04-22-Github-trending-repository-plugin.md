---
layout: post
title: Github Trending Repositories WordPress plugin
comments: true
---

The [WordPress](http://www.WordPress.org) world is fascinating. The WordPress both as a cms and a blogging platform is awesome. When it comes to extending the WordPress capabilites plugins are the go-to solutions. The main benefit behind using plugins is the loose coupling they provide in our code which WordPress as a whole constantly strives for. This loose coupling not only helps in the maintenance of our code but also its reuse.Striving in the direction i made another step at building some useful plugin that didn't already exist on the WordPress [plugin directory](http://www.WordPress.org/plugins/). This time the idea was building a simple widget that showed the latest [trending repositories on github](https://github.com/trending).

  >The challenge here was that the github api doesn't provide anyway to  retrieve the trending repositories but i overcame it by building a rest api using some online service that constantly crawles the [trending page](https://github.com/trending) for data.


   So i was on track to building the **150** loc. The  widget shows latest top six trending projects on github.The data is cached using the WordPress transient api for 30  minutes before being discarded. The sole aim behind caching was to prevent too many requests and it also was in line with the rate at which  the list of trending repos changes on github. The plugin can be found [here](https://WordPress.org/plugins/github-trending-repositories/) in its glory.
