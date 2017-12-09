---
layout: post
title:  "How to send iOS push notifications"
date:   2017-12-9 17:56:40 +0100
categories: ios push-notifications
---
This article explains how to send iOS push notifications with [PhoneGap](https://phonegap.com/).

As written in [this tutorial](http://docs.phonegap.com/tutorials/develop/push-notifications/), create a project from a template, and `cd` into the `www/` folder:

```
phonegap create --name "pushNotification" --id "com.myapp.sample" --template push
cd pushNotification/www
```

Then start the development server and install the app on your smartphone:

```
phonegap serve
```

Install the [PhoneGap Developer](https://itunes.apple.com/us/app/phonegap-developer/id843536693?mt=8) app on your iPhone and browse to the server address. Take the `Device Push ID` and send the notification:

```
phonegap push --deviceID someID --service apns --payload '{"aps": {"title": "Title", "alert": "Hello World"}}'
```
