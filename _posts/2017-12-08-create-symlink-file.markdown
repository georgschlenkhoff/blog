---
layout: post
title:  "Create a symlink file with Linux"
date:   2017-12-08 23:59:40 +0100
categories: linux
---
A symlink can be created a follows:

```
ln -s /path/to/folder/that/you/want/to/sync ~/Dropbox/folder/name
```

NOTE when using with [Dropbox](https://www.dropbox.com/): The original file will need to have permissions set to 664 at minimum otherwise the new link in the folder will have a red X on its icon, meaning it won't copy file to the Dropbox server. It should look like this:

```
-rw-rw-r--  1 owner  group  82894 Oct 22 22:22 file.abc
```
