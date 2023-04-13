# Django Tutorial for Beginners - 12 - Writing Another View

Week 15.3 | Wednesday, April 12, 2023 | 05:51 PM

related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) -
source : <https://youtu.be/mWofrhTwGWQ>

## Writing Another View - TL;DR

```python
# pattern : /music/album_id/
re_path(r'^(?P<album_id>[0-9]+)/$', views.detail, name='detail'),
path('<int:album_id>/', views.detail, name='detail'),
```

1. Look for whatever URL the user typed in
    1. `r'^(?P<album_id>[0-9]+)/$'`
    2. `'<int:album_id>/'
2. Connect it to the corresponding functions in the view.py file
    1. `views.detail`
3. Give the path a name that matches the function in the view.py file
    1. `name='detail'`

## Writing Another View

Creating a view -> creating another webpage

A view is a function that returns a HTML (ie. `HttpResponse()`). Each URL/URL pattern is connected to a view.

Every view function is going to take a `request` : a HTML request (a webpage, an image, etc.).
`request` (_type_): this is always the first argument of any view function.

We have not connected the logic to the database, so there won't be validation to the variables (`album_id`).

Simplified : each URL/URL pattern is connected to a HTML response

```python
# website\music\urls.py
from django.urls import path, re_path
from . import views

urlpatterns = [
    # pattern : /music/
    re_path(r'^$', views.index, name='index'),
    # pattern : /music/album_id/
    re_path(r'^(?P<album_id>[0-9]+)/$', views.detail, name='detail'),
    # OR the same - pattern : /music/album_id/
    path('<int:album_id>/', views.detail, name='detail'),
]
```

```python
# website\music\views.py
from django.http import HttpResponse  # basic HTML code or a redirect.

def index(request):
    """Returns the homepage for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.

    Returns:
        _type_: HttpResponse object.
    """
    return HttpResponse("<h1>This is the Music app homepage.</h1>")

def detail(request: any, album_id: int) -> HttpResponse:
    """ Returns the details for the album with the given album_id.

    Args:
        request (_type_): this is always the first argument of any view function.
        album_id (int): the id of the album.

    Returns:
        _type_: HttpResponse object.
    """
    return HttpResponse("<h2>Details for Album id: " + str(album_id) + "</h2>")
```
