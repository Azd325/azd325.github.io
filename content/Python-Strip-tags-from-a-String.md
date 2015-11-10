---
title: Python - Strip tags from a String
author: Tim Kleinschmidt
date: 2013-08-18 23:21:00
category: Python
---

This is a little snippet to remove tags from a string to get the only raw textual content. I'm using the Beautiful Soup Library [[1]](#f1) for this job.

Install Beautifulsoup with pip:

``` bash 
pip install beautifulsoup4
```

Example:

``` python 
from bs4 import BeautifulSoup
html = "&lt;html&gt;&lt;body&gt;&lt;h1&gt;Test&lt;/h1&gt;&lt;body&gt;&lt;html&gt;"
''.join(BeautifulSoup(html).get_text())
```

[#f1]: http://www.crummy.com/software/BeautifulSoup/bs4/doc/ "Beautifulsoup Documentation"
