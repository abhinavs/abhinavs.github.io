---
layout: post
title: Mac - How to fix Python error "ERROR:root:code for hash md5 was not found"
excerpt: "This error is actually because of Homebrew and not exactly because of Python"
tags: [Python, Mac, OSX, Error, Fix, Brew, Tech, TechNotes, OpenSSL, Homebrew]
comments: true
canonical_url: 'https://www.abhinav.co/fix-python-error-root-code-for-hash-md5-not-found'
---
While trying to install a few packages using [Pip](https://pypi.org/project/pip/), I encountered following error: "ERROR:root:code for hash md5 was not found". For reference, here is the **stacktrace** that I saw:
```
ERROR:root:code for hash md5 was not found.
Traceback (most recent call last):
  File "/usr/local/Cellar/python@2/2.7.15_1/Frameworks/Python.framework/Versions/2.7/lib/python2.7/hashlib.py", line 147, in <module>
    globals()[__func_name] = __get_hash(__func_name)
  File "/usr/local/Cellar/python@2/2.7.15_1/Frameworks/Python.framework/Versions/2.7/lib/python2.7/hashlib.py", line 97, in __get_builtin_constructor
    raise ValueError('unsupported hash type ' + name)
ValueError: unsupported hash type md5
```

<br />
**Fix**
<br />
It took me a while to figure out the error is not exactly because of Python, but [OpenSSL](https://www.openssl.org/) and [Homebrew](https://brew.sh/). Fix is quit simple, you need to switch Homebrew to use right version of open SSL. 

```
$ ls /usr/local/Cellar/openssl  # find out which version of openssl is currently present
1.0.2q
$ brew switch openssl 1.0.2q    # and switch to that version
```

