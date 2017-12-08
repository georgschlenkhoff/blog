---
layout: post
title:  "How to decrypt a SQLite database"
date:   2017-12-8 23:32:40 +0100
categories: sqlite
---
This article explains how you decrypt a SQLite database that was encrypted with [SQLCipher](https://github.com/sqlcipher/sqlcipher) via terminal.

###1. Create a database script

```
PRAGMA key = 'yourpwd';
ATTACH DATABASE '/Users/user/full-path/my.db' AS plaintext KEY '';
SELECT sqlcipher_export('plaintext');
DETACH DATABASE plaintext;
```

###2. Read in the script with sqlcipher

```
sqlcipher yourdb.sqlite < script.sql
```
