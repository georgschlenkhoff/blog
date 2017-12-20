---
layout: post
title:  "Fugitive Cheat Sheet"
date:   2017-12-20 23:06:40 +0100
categories: vim, git
---
This article gives an overview of main [Fugitive](https://github.com/tpope/vim-fugitive) commands. See [these tutorials](http://vimcasts.org/episodes/fugitive-vim---a-complement-to-command-line-git/).

```
# Checkout new branch
:Git co experimental

# Checkout latest branch
:Git checkout

# Checkout latest current file
:Git checkout %
:Gread

# Checkout version from HEAD commit
: Gread -

# Add current file to index
:Git add %
:Gwrite

# Move current file
:Git mv % target_path
:Gmove target_path

# Remove current file
:Git rm %
:Gremove

# See git blames
:Gblame

# See git status
# Add/remove file form index with '-'
# Jump to next file with 'ctrl-p' and 'ctrl-n'
# Commit with 'shift-c'
# Amend change with 'ca'
:Gstatus

# Show git diff
:Gdiff
```

![diffget matrix]({{ "assets/diffget-diffput-matrix.png" | absolute_url }})
![Gread matrix]({{ "assets/Gread-Gwrite-matrix.png" | absolute_url }})
