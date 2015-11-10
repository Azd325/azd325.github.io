---
title: Django - Setting Headers in your Response
author: Tim Kleinschmidt
date: 2012-03-21 10:20
category: Python
---

Today I found a interesting part in the  [Django Docs](https://docs.djangoproject.com/en/dev/ "Django Docs")
about **set** and **remove** of [Headers](http://en.wikipedia.org/wiki/List_of_HTTP_header_fields/ "Wikipedia Article about Headers") in responses .

``` python
response = HttpResponse()  # Created a HttpResponse
response['Cache-Control'] = 'no-cache'  # Set Cache-Control Header
del response['Cache-Control']  # Remove Cache-Control Header
```

I know that should be do the web server like [Apache](http://apache.org/ "Apache") but sometimes is it nicer (even recommended) to set in some
cases the headers in web app directly, to test the behaviour or to make really sure to get
the right headers in the response if you don't have anytime access to the
server config's or a lazy sys-admin.

__For you interest:__

[Set and Remove in the Django Docs][#f1]
[Content-Disposition example][#f2]

[#f1]: https://docs.djangoproject.com/en/dev/ref/request-response/#setting-headers/ "Set and Remove in the Django Docs"
[#f2]: https://docs.djangoproject.com/en/dev/ref/request-response/#telling-the-browser-to-treat-the-response-as-a-file-attachment/ "Content-Disposition example"
