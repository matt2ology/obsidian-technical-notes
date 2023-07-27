# Django Tutorial for Beginners - 20 - Removing Hardcoded URLs

Week 15.6 | Saturday, April 15, 2023 | 10:41 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [05 - Views](05%20-%20Views.md)

Source : <https://youtu.be/XQll-WgZcpE>

Best practice to remove hardcoded URLs, so if a site re-structure or the move of files is required the links to those respective pages won't break.

In `re_path(r'^(?P<album_id>[0-9]+)/$', views.detail, name='detail')`, the `name` argument/parameter is a variable that references the first argument/parameter URL pattern.

To make the dynamic pattern we use `{% url 'pathPatternName' theModelTableNumID %}`

```python
# website\music\urls.py
from django.urls import path, re_path
from . import views

urlpatterns = [
    # 'index' is a variable that references URL pattern : /music/
    re_path(r'^$', views.index, name='index'),
    # 'detail' is a variable that references URL pattern : /music/someNumber/
    re_path(r'^(?P<album_id>[0-9]+)/$', views.detail, name='detail'),
    # Alternatively you can do the following
    path('<int:album_id>/', views.detail, name='detail'),
]
```

```html
<!-- website\music\templates\music\index.html -->
<!-- Hardcoded URL -->
<main>
  <h1>Albums</h1>
  {% if all_albums %}
  <ul>
    {% for album in all_albums %}
    <li><a href="/music/{{ album.id }}/">{{ album.album_title }}</a></li>
    {% endfor %}
  </ul>
  {% else %}
  <h2>No albums are available.</h2>
  {% endif %}
</main>
```

```html
<!-- website\music\templates\music\index.html -->
<!-- Removed Hardcoded URLs - Dynamic URL -->
<main>
  <h1>Albums</h1>
  {% if all_albums %}
  <ul>
    {% for album in all_albums %}
    <li><a href="{% url 'detail' album.id %}">{{ album.album_title }}</a></li>
    {% endfor %}
  </ul>
  {% else %}
  <h2>No albums are available.</h2>
  {% endif %}
</main>
```
