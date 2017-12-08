---
layout: post
title:  "Download a Dropbox file with JS SDK"
date:   2017-12-9 00:43:40 +0100
categories: dropbox js linux
---
This article explains how to download a [Dropbox](https://www.dropbox.com/) file with the [Dropbox JS SDK](https://dropbox.github.io/dropbox-sdk-js/).

First install the [Dropbox node package](https://github.com/dropbox/dropbox-sdk-js) to your project:

```
npm install --save dropbox
```

You need to generate an app first in the [App Console](https://www.dropbox.com/developers/apps). Click on that button:

![Dropbox - Generate access token]({{ "assets/dropbox-generate-access-token.png" | absolute_url }})

Paste the access token in the `accessToken` variable in your code. And also create a url of the file that you want to share.

```
var fs = require('fs');
var Dropbox = require('dropbox');
var dbx = new Dropbox({ accessToken: 'YOUR-ACCESS-TOKEN' });
dbx.sharingGetSharedLinkFile({url: 'http://yourlink-of-dropbox-file'})
  .then(function(data) {
    fs.writeFile("./myfile", data.fileBinary, 'binary', function(err) {
      if(err) {
        console.log("err", err);
      } else {
        console.log('File saved');
      }
    }); 
  })
  .catch(function(error) {
    console.error(error);
  });
  ```
