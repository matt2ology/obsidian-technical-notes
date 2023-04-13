# Django Tutorial for Beginners - 15 - Render Template Shortcut

Week 15.4 | Thursday, April 13, 2023 | 12:19 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [14 - Templates](14%20-%20Templates.md)

Source : <https://youtu.be/RkBL9pAF8As>

GitHub permalink : [def index(request: any) -> HttpResponse:](https://github.com/matt2ology/django-thenewboston/blob/139864863b7e42527311b3619e91c6cb14170e22/website/music/views.py#L26-L39)

A quicker way to render a HTTP response

```python
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
```

From this longer verbose method

```python
def index_old_long_way(request: any) -> HttpResponse:
    """ Returns the index page for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.

    Returns:
        _type_: HttpResponse object.
    """
    # get all the albums from the database, so we can pass it to the template.
    ALL_ALBUMS: object = Album.objects.all()
    # load the template, so we can pass it to the HttpResponse object.
    TEMPLATE: object = loader.get_template('music/index.html')
    # CONTEXT is a dictionary that maps template variable names to Python objects.
    CONTEXT: dict = {
        'all_albums': ALL_ALBUMS,
    }
    return HttpResponse(TEMPLATE.render(CONTEXT, request))
```
