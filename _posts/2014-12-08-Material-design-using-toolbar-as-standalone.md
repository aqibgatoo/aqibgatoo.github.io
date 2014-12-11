---
layout : post
title: Material Design Using Toolbar as Standalone
comments: true
---

This post is related to my last [post](http://aqibgatoo.com/2014/11/20/Material-Design-for-pre-lollipop-devices/) where i discussed using toolbar as an action bar. In this post i will discuss using it as standalone, now the situations will you be using the toolbar as a standalone may be summarized as

- Show multiple toolbars.
- Vary the width of the toolbar etc.

Here you see how to use it as standalone

{% highlight java %}
@Override
public void onCreate(Bundle savedInstanceState) {
  super.onCreate(savedInstanceState);
  setContentView(R.layout.my_layout);

  Toolbar toolbar = (Toolbar) findViewById(R.id.my_basic_toolbar);

  // Set an OnMenuItemClickListener to handle menu item clicks
  toolbar.setOnMenuItemClickListener(
    new Toolbar.OnMenuItemClickListener() {
      @Override
      public boolean onMenuItemClick(MenuItem item) {
        // Handle the menu item
        return true;
      }
      });

      // Inflate a menu to be displayed in the toolbar
      toolbar.inflateMenu(R.menu.my_toolbar_menu);
    }
{% endhighlight %}

#####Note
> when using toolbar as standalone we don't have to disable the action bar.Rest things are same as discussed in my previous [post]("http://aqibgatoo.com/2014/11/20/Material-Design-for-pre-lollipop-devices/")
