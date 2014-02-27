---
layout: post
title: "Creating An App In Two Days"
date: 2014-02-27 11:22:51 -0500
comments: true
categories: [Development, Projects]
---

Sometimes you come up with an idea for an app, but you aren't sure if there really is a market for it. It seems like a good idea but you don't want to spend a lot of time and resources to create and deploy something that there may not be an interest for. In those cases it can be helpful to deploy the skeleton of your application and deploy it as quickly as possible, as a way to not only gain an idea of if there's an interest in it, but also what features your end user may be looking for.
<!-- more -->
{% img /images/juicevault.png 'JuiceVault' %}

We developed [JuiceVault](http://www.myjuicevault.com) in just two days using Ruby on Rails. It's an enthusiast site that we weren't sure people would really take to, but after posting it to reddit we had over 80 users signed up in just 24 hours. We developed it as quickly as we could and deployed it to [Heroku](http://www.heroku.com) knowing we could scale up as the app grew. To monitor the app's performance we used [New Relic](http://www.newrelic.com) which is trivially easy to integrate with a Rails app. This combination of technologies enables rapid application development, and helped us decide whether this app was something we should persue. We think there's definitely a need for our application and will continue to develop it over the coming weeks, hopefully adding all of the features our users would like to see.