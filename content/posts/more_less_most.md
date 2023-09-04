---
title: "more vs less vs most"
date: 2019-05-27
description: ""
featured_image: ""
tags: ["#linux", "#note"]
draft: false
---

# more vs less vs most

> There is an old joke consisting of three words: “less is more”. (This is the “pun” referred to by guillermo chamorro's second comment to the question.) Perhaps one reason why people like the joke so much is that the statement can be understood in three different ways, and so there isn't any clarity about which way is meant. Yet, all three of the ways are accurate, at least on some operating systems. (Point #2 might not apply to Ubuntu, and I do understand that this is an Ubuntu-focused site. However, Ubuntu derives from Debian wish has strong history of ideas being taken from, and shared with, the rest of Unix and Unix-ish systems. So, understanding what other operating systems do isn't a bad thing.)


[more](https://manpages.ubuntu.com/manpages/bionic/man1/more.1.html) is the oldest, [less](https://manpages.ubuntu.com/manpages/bionic/en/man1/less.1.html) is an improvement and [most](https://manpages.ubuntu.com/manpages/bionic/en/man1/most.1.html) is an improvement on that.

Short comparison:
* `more`: forward navigation and limited backward navigation.
* `less`: both forward and backward navigation and also has search options. You can go to the beginning and the end of a file instantly. Plus you can switch to an editor (like open the file in vi or vim). It is noticeably quicker than editor for when the file is large. The `less` command supports a shell/environment variable named `LESS_IS_MORE`. The `less` command acts quite a bit like the older more command by default, but if the `less` command sees this variable is set to a value of 1 (the number one), then the `less` command will offer fewer features in an attempt to be increase just how compatible it is with the older pager command that is named `more`.

* `most`: has all the features of more and less but you can also open multiple files, close 1 file at a time when you have multiple files open, allows locking and scrolling of the open windows and allows for splitting of open windows.

UPD:
[bat](https://github.com/sharkdp/bat) as cat(1) clone with syntax highlighting and Git integration.

## Links:

https://askubuntu.com/questions/1191862/what-is-the-difference-between-more-and-less-commands