---
title: Django - Pre-Validation with the URL dispatcher
author: Tim Kleinschmidt
date: 2012-03-22 15:20
category: Python
---

I work currently on a rating feature, to rate some items and I want to do this
in one view to handle the methods *POST* and *GET*.

*POST* should handle the submit request(rate count) of the item

*GET* should handle the template with the right item to see the current
user/ global rate

**Situation:**

 * max. stars = five
 * min. stars = one
 * zero stars are not possible to vote

**What we need to rate?**

 * item id
 * vote result

I start to add the first version of the view and I was adding two URL's one for *GET* and one for *POST*.
And I what to handle the parameter over the named groups in Django.

``` python
urlpatterns += patterns('',
    url(r'^ajax/votes/(?P<item_id>\w+)/$', 'vote_for_item'),  # GET
    url(r'^ajax/votes/(?P<item_id>\w+)/(?P<vote>\d+)/$', 'vote_for_item')  # POST
)
```


*What we can to be more explicit?*

We can use `re` of Python and so we can set a range of allowed numbers with `[1-5]`.
So we have only a range of URL's for every state of the rating situation and so we get a *404* if we want to access for example the vote-URL with the vote count of six.

``` python
urlpatterns += patterns('',
    url(r'^ajax/votes/(?P<item_id>\w+)/$', 'vote_for_item'),  # GET
    url(r'^ajax/votes/(?P<item_id>\w+)/(?P<vote>[1-5])/$', 'vote_for_item')  # POST
)
```

The next thing we have to two exact same URL's the only difference is that the *POST* needs an extra parameter.

*Can we make this parameter optional?*

Yeah, we can do it again with `re`. We have to wrap the vote part in `(?:...)` and after it a single `?`. More in the Python Docs.

**The end solution:**

I have one URL for the cases of *GET* and *POST* and we create only the URL's what I need for the rating feature

``` python
urlpatterns += patterns('',
    url(r'^ajax/votes/(?P<item_id>\w+)/(:?(?P<vote>[1-5])/)?$', 'vote_for_item'),
)
```

**FYI:**

[Optional named groups Python re](http://stackoverflow.com/questions/8270439/optional-named-groups-python-re "Stackoverflow Question")

[URL dispatcher at Django Docs](https://docs.djangoproject.com/en/dev/topics/http/urls/ "Django documentation")

[re at Python Docs](http://docs.python.org/library/re.html "Python documentation")
