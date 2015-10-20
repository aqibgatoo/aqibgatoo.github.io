---
layout : post
title: C# Interpolated Strings
tags: C# 6.0,Strings
comments: true
---


I was recently working on a project where i had to write queries to fetch data from Sql Server. The worst nightmare is when tables names are dynamic that is table names are based on certain parameters.The trick to querying the particular table on the basis of parameter passed is using **string.Format()** . It can be used to create the query and passing table name as parameter but this becomes cubersome and error prone because you have to keep track of the placeholders like **{0},{1}** etc


**C# 6.0** string interpolation elegantly solves this problem and this probably my loved feature of C# 6. So instead of writing things like

{% highlight c# %}
var query = string.Format("Select * from example_table_{0}",parameterName);
{% endhighlight %}

we could easily write it using string interpolation as

{% highlight c# %}
var query = $"select * from example_table_{parameterName}";
{% endhighlight %}

These placeholders in C# 6.0 are known as **holes**. It doesn't stop here we can even pass optional alignment and format specifiers as we would in case of string.Format(). Also the contents of holes can include expressions as well as other strings e.g

{% highlight c# %}
var query = $"select * from example_table_{(parameter!=null?parameter:"default")}";
{% endhighlight %}

>Keep an eye the  **"default"** is a string inside of the expression
