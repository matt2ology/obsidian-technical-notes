# Django Tutorial for Beginners - 16 - Raising a 404 HTTP Error

Week 15.4 | Thursday, April 13, 2023 | 12:34 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [21 - Namespace and HTTP 404 Shortcut](21%20-%20Namespace%20and%20HTTP%20404%20Shortcut.md)

Source : <https://youtu.be/LLcAr3HS8qA>

GitHub permalink :

To enable/invoke HTTP 404 error codes when the end user attempts to assess a webpage that does not exist we do the following

Import `from django.http import Http404  # raise an Http404 exception.`

Instead of returning some HTTP response without checking if the an ID is valid we should query the database and see if there is a database with the ID requested. If it exists return via template; otherwise, we'd want to send back an HTTP 404 error response.

```python
from .models import Album  # import the Album model from the models.py file.

from django.http import Http404  # raise an Http404 exception.
from django.http import HttpResponse  # basic HTML code or a redirect.
from django.shortcuts import render  # render a template and pass it a context.


def index(request: any) -> HttpResponse:
    """ Returns the index page for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.

    Returns:
        _type_: HttpResponse object.
    """
    # get all the albums from the database, so we can pass it to the template.
    ALL_ALBUMS: object = Album.objects.all()
    # CONTEXT is a dictionary that maps template variable names to Python objects.
    CONTEXT: dict = {'all_albums': ALL_ALBUMS}
    return render(request, 'music/index.html', CONTEXT)


def detail(request: any, album_id: int) -> HttpResponse:
    """ Returns the detail page for the Music app.

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

def detail_the_old_way(request: any, album_id: int) -> HttpResponse:
    """ Returns the detail page for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.
        album_id (int): the id of the album.

    Returns:
        _type_: HttpResponse object.
    """
    return HttpResponse("<h2>Details for Album id: " + str(album_id) + "</h2>")


```
