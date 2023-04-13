# Django Tutorial for Beginners - 5 - Views

Week 14.3 | Wednesday, April 05, 2023 | 09:22 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [Django Project Template File Explanation](Django%20Project%20Template%20File%20Explanation.md) - [Django App Template File Explanation](Django%20App%20Template%20File%20Explanation.md)
Source : <https://youtu.be/nAn1KpPlN2w>

When a user request anything from the website Django will project titled subfolder
and looks to the `urls.py` file.

This file, `urls.py`, contains the URL-mappings.

Django looks at the URL : `http://127.0.0.1:8000/admin/`

- The domain name/IP address of the server : `127.0.0.1:8000`
- The actual part that matters - the part that Django cares about with URLs : `admin/`
  - Django looks at the `re_path()` pattern with REGEX

All URLs of a particular app should be placed in that specific app directory: we can add our own `urls.py` file in that directory and then import it into the overall website `urls.py`

The `views.py` takes a request and sends back a HTTP response.

> The workflow
>
> > `website\website\urls.py` -> `website\music\urls.py` -> `website\music\urls.py`

```txt
# Parent folder website - folder structure created
└───website_project_folder
    │   db.sqlite3
    │   manage.py
    │
    ├───music                 # <- Can add in our own urls.py file
    │   │   admin.py
    │   │   apps.py
    │   │   models.py
    │   │   tests.py
    │   │   views.py
    │   │   __init__.py
    |   |   urls.py           # <- Add in our own urls.py file
    |   |                     # Purpose is to create urls just for music
    │   │
    │   └───migrations
    │           __init__.py
    │
    └───website              # <- this sub-folder must be left the same
            asgi.py
            settings.py
            urls.py          # <- First thing Django looks at on user request
            wsgi.py
            __init__.py
```

```python
# website\music\urls.py
from django.urls import path, re_path
from . import views # . means current directory (music) and import views.py file

urlpatterns = [
		# Regex starts with carrot (^) and ends with a dollar ($)
   re_path(r'^$', views.index, name='index'), # Default homepage
   re_path('^songs$', views.songs, name='songs'), # REGEX Pattern, response
   re_path('^id$', views.id, name='id'),
   re_path('^delete_music$', views.delete_music, name='delete_music'),

	# OR just provide simple, plain, boring string
   path('', views.index, name='index'), # Default homepage
   path('songs', views.songs, name='songs'), # REGEX Pattern, response
   path('id', views.id, name='id'),
   path('delete_music', views.delete_music, name='delete_music'),
]
```

```python
# website\website\urls.py
from django.contrib import admin
from django.urls import path, re_path
from django.urls import include # allows referencing other URLconfs.

urlpatterns = [
    # q: whats the difference between path and re_path?
    # a: a path is a string, a re_path is a regex.
    # q: whats the difference between a URL Resolver and a URL Pattern?
    # a: a URL Resolver is a regex, a URL Pattern is a string.
    path('admin/', admin.site.urls),
    re_path(r'^music/', include('music.urls')),
]
```

```python
# website\music\views.py
from django.http import HttpResponse # basic HTML code or a redirect.

def index(request):
    """Returns the homepage for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.

    Returns:
        _type_: HttpResponse object.
    """
    return HttpResponse("<h1>This is the Music app homepage.</h1>")
```
