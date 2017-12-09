---
layout: post
title:  "Execute shell command from NodeJS"
date:   2017-12-9 18:25:40 +0100
categories: ios push-notifications
---
This article explains how to use [child_process.exec](https://nodejs.org/docs/v8.1.4/api/child_process.html#child_process_child_process_exec_command_options_callback) within NodeJS.

```
const util = require('util');
const exec = util.promisify(require('child_process').exec);

async function lsExample() {
  const { stdout, stderr } = await exec('ls');
  console.log('stdout:', stdout);
  console.log('stderr:', stderr);
}
lsExample();
```
