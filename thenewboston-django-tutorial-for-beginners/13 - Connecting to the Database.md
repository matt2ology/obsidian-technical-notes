# Django Tutorial for Beginners - 13 - Connecting to the Database

Week 15.3 | Wednesday, April 12, 2023 | 07:02 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [14 - Templates](14%20-%20Templates.md) - [12 - Writing Another View](12%20-%20Writing%20Another%20View.md) - [09 - Database API](09%20-%20Database%20API.md) - [18 - Related Objects Set](18%20-%20Related%20Objects%20Set.md)

Reference : <https://www.w3schools.com/tags/att_a_href.asp>

Source : <https://youtu.be/b0d09mYsORs>

## Connecting to the Database

To connect to the database we must import the corresponding tables from models.py file in our views.py file.

All of the database API methods work and are available in views.py script file.

Proper development we'd want to reduce the amount of embedded HTML from our Python view.py code.

```python
# website\music\views.py
from django.http import HttpResponse  # basic HTML code or a redirect.
from .models import Album # import the Album model from the models.py file.


def index(request: any) -> HttpResponse:
    """ Returns the index page for the Music app.

    Args:
        request (_type_): this is always the first argument of any view function.

    Returns:
        _type_: HttpResponse object.
    """
    ALL_ALBUMS: object = Album.objects.all()
    HTML: str = ''
    for album in ALL_ALBUMS:
        # URL pattern: /music/album_id/
        URL = '/music/' + str(album.id) + '/'
        # HTML <a> href Attribute
        # <a href="https://www.w3schools.com">Visit W3Schools</a>
        HTML += 'Album Title :<a href="' + URL + '">' + album.album_title + '</a><br>'
    return HttpResponse(HTML)
```

```python
# website\music\models.py
class Album(models.Model):
    """
    Album model that has the following attributes:
    `artist`, `album_title`, `genre`, and `album_logo`.
    """
    # The primary key is automatically created by Django and is called id.
    # But we can also create our own primary key by adding the following line:
    # `id = models.AutoField(primary_key=True)`
    artist = models.CharField(max_length=250)
    album_title = models.CharField(max_length=500)
    genre = models.CharField(max_length=250)
    # URL to album logo image file
    album_logo = models.CharField(max_length=1000)

    def __str__(self):
        """This is what will be displayed in the admin page
        for each album object created in the database
        (instead of Album object (1), Album object (2), etc.)

        Returns:
            [string] -- [artist name - album title]
        """
        return self.album_title + ' - ' + self.artist
```
