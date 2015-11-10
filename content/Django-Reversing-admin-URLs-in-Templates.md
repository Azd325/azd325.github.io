---
title: Django - Reversing admin URLs in Templates
author: Tim Kleinschmidt
date: 2013-04-04 17:11
category: Python
---

``` python
{% raw %}
{% url admin:index %}
{% url admin:polls_choice_add %}
{% url admin:polls_choice_change choice.id %}

# For Django 1.5. Thanks to Kenneth Love
{% url 'admin:index' %}
{% url 'admin:polls_choice_add' %}
{% url 'admin:polls_choice_change' choice.id %}
{% endraw %}
```


With this Code Examples you can manage to get the right url in the templates where you want.

1. Is the index url of the admin.

2. Is the add url for the App Polls with the Model Choice.

3. Is the change url for the App Polls with the Model Choice and with Parameter for that object what you want to change.

The principe is *{{ app_label }}_{{ model_name }}_change object_id*

This help me today a lot at work.

__For you interest:__

[Django Docs:Reversing Admin Urls][#f1]
[Kenneth Love][#f2]

[#f1]: https://docs.djangoproject.com/en/dev/ref/contrib/admin/#reversing-admin-urls/ "Django Docs: Reversing Admin Urls"
[#f2]: http://gigantuan.net/ "Kenneth Love"
