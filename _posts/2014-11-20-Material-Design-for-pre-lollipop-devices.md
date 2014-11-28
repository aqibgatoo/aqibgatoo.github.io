---
layout: post
title: Material Design for pre lollipop devices
---
With the release of Android 5.0 a.k.a Lollipop new features were added to the android ecosystem,but the top most notable feature of android 5.0 is the Material Design Spec.
The most notable feature for any android app is is <b>Toolbar</b> widget.

> This is a generalization of the ActionBar pattern but gives you much more control and flexibility in using it. Toolbar is a view in your hierarchy just like any other, making it easier to interleave with the rest of your views, animate, react to scroll events.

### How to use.
   If you’re using Gradle then the first thing to do is to add appcompat as a dependency in your build.gradle:

{% highlight java %}
   dependencies {
     ...
     compile "com.android.support:appcompat-v7:21.0.+"
   }
{% endhighlight %}

  There are two ways for using Toolbar either standalone or Action bar. I will discuss using it as an Aciton bar.

-   Firstly the Activity should extend from ActionBarActivity but note to use import it from appcompact-v7.
-  Change the values/themes.xml:

{% highlight xml %}
<style name="Theme.MyTheme" parent="Theme.AppCompat.Light.NoActionBar">
<!-- Here we setting appcompat’s actionBarStyle -->
<item name="actionBarStyle">@style/MyActionBarStyle</item>

<!-- ...and here we setting appcompat’s color theming attrs -->
<item name="colorPrimary">@color/my_awesome_red</item>
<item name="colorPrimaryDark">@color/my_awesome_darker_red</item>

<!-- The rest of your attributes -->
</style>
{% endhighlight %}

- You need to create a Toolbar instance, usually via your layout XML:

{% highlight xml %}
<android.support.v7.widget.Toolbar
xmlns:app="http://schemas.android.com/apk/res-auto"
android:id="@+id/my_basic_toolbar"
android:layout_height="wrap_content"
android:layout_width="match_parent"
android:minHeight="?attr/actionBarSize"
android:background="?attr/colorPrimary" />
{% endhighlight %}

- Then add the toolbar layout to your activity
layout as:

{% highlight xml %}
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<include layout="@layout/toolbar" />

</RelativeLayout>
{% endhighlight %}

- Final step is to to set your Toolbar as your action bar in the Activity.java:

{% highlight java %}
@Override
public void onCreate(Bundle savedInstanceState) {
  super.onCreate(savedInstanceState);
  setContentView(R.layout.my_layout);

Toolbar toolbar = (Toolbar) findViewById(R.id.my_basic_toolbar);
  setSupportActionBar(toolbar);
}
{% endhighlight %}

This is the Result:

![a relative link](/images/material_design_result.png)
