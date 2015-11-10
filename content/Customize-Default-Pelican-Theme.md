---
title: Customize Default Pelican Theme
author: Tim Kleinschmidt
date: 2013-09-17 22:50:18
category: Python
---

I wanted to customize the default theme of Pelican but didn't want to copy single
template files or to edit the files in the python path.

In the docs you can find how you install, remove and list themes [[1]][#f1]

``` bash 
pelican-themes -v -l
```

You'll get some output like this

``` bash 
/home/tim/.virtualenvs/pelican-blog/lib/python2.7/site-packages/pelican/themes/simple
/home/tim/.virtualenvs/pelican-blog/lib/python2.7/site-packages/pelican/themes/notmyidea
```

So what I did:

1.  Go to your root blog folder
2.  Then copy the complete &quot;`<span class="n">notmyidea</span>`&quot; folder to your current pelican root folder

``` bash 
# Create themes folder
mkdir themes
# Copy the folder
cp -R /home/tim/.virtualenvs/pelican-blog/lib/python2.7/site-packages/pelican/themes/notmyidea themes/
```

3. After it you have to define in your *pelicanconf.py* a theme variable *THEME*. [[2]][#f2]
What gets linked to the copied theme folder!

``` python
THEME = "themes/notmyidea"
```

4. Now you are in the state to customize the default template to your style.

[#f1]: http://docs.getpelican.com/en/3.2/pelican-themes.html "Pelican Themes"
[#f2]: http://docs.getpelican.com/en/3.2/settings.html#themes "Themes Documentation"
