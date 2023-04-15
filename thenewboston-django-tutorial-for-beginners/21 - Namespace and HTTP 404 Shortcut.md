# Django Tutorial for Beginners - 21 - Namespace and HTTP 404 Shortcut

Week 15.6 | Saturday, April 15, 2023 | 11:49 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [16 - Raising a 404 HTTP Error](16%20-%20Raising%20a%20404%20HTTP%20Error.md) - [20 - Removing Hardcoded URLs](20%20-%20Removing%20Hardcoded%20URLs.md)

Source : <https://youtu.be/vhBxt9T4Zvk>

## Namespaces

What happens when you have multiple apps with templates of the same name (i.e. `detail`)?

1. Make a namespace variable assigned to a string of the app's name in the app's URL.py file
   1. `app_name : str = 'music'  # this is the namespace for the Music app.`
2. Prepend the pattern name with the value of the namespace variable in the corresponding template html page.
   1. For example, `{% url 'detail' album.id %}` becomes `{% url 'music:detail' album.id %}`

Having this allows us to have multiple path name variable of the same name across multiple apps

## HTTP 404 Shortcut

Include `from django.shortcuts import render, get_object_or_404`

Replace try/except block with the function : `ALBUM = get_object_or_404(Album, pk=album_id)` with an argument of the Python class model/table and the corresponding private key.

## Namespaces Code Example

```python
# website\music\urls.py
from django.urls import path, re_path
from . import views

app_name : str = 'music'  # this is the namespace for the Music app.

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
<main>
  <h1>Albums</h1>
  {% if all_albums %}
  <ul>
    {% for album in all_albums %}
    <li>
      <a href="{% url 'music:detail' album.id %}">{{ album.album_title }}</a>
    </li>
    {% endfor %}
  </ul>
  {% else %}
  <h2>No albums are available.</h2>
  {% endif %}
</main>
```

## HTTP 404 Shortcut Code Examples

### 404 Error Code Via Try/Except

```python
# website\music\views.py
from .models import Album  # import the Album model from the models.py file.

from django.http import Http404  # raise an Http404 exception.
from django.http import HttpResponse  # basic HTML code or a redirect.
from django.shortcuts import render  # render a template and pass it a context.

def detail_the_old_way(request: any, album_id: int) -> HttpResponse:
    """ Returns the detail page for the Music app.
   
    Needs : `from django.http import Http404`  # raise an Http404 exception

    Args:
        request (_type_): this is always the first argument of any view function.
        album_id (_type_): the id of the album.

    Returns:
        _type_: HttpResponse object.
    """
    try:
        ALBUM: object = Album.objects.get(pk=album_id)
    except Album.DoesNotExist:
        raise Http404("Album does not exist")
    return render(request, 'music/detail.html', {'album': ALBUM})
```

### 404 Error Code Without Try/Except Block

```python
# website\music\views.py
from .models import Album  # import the Album model from the models.py file.

from django.http import HttpResponse  # basic HTML code or a redirect.
from django.shortcuts import render, get_object_or_404  # render a template.

def detail(request: any, album_id: int) -> HttpResponse:
    """ Returns the detail page for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.
        album_id (_type_): the id of the album.

    Returns:
        _type_: HttpResponse object.
    """
    ALBUM = get_object_or_404(Album, pk=album_id) # removes the need for try/except block.
    return render(request, 'music/detail.html', {'album': ALBUM})
```
