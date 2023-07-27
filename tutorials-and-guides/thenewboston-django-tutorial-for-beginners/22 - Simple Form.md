# Django Tutorial for Beginners - 22 - Simple Form

Week 15.6 | Saturday, April 15, 2023 | 12:37 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [06 - Database Setup](06%20-%20Database%20Setup.md) - [09 - Database API](09%20-%20Database%20API.md) - [23 - Adding Forms to the Template](23%20-%20Adding%20Forms%20to%20the%20Template.md)

Source : <https://youtu.be/wDuqObGbLnI>

We'd want to create a URL map, URLs aren't always one-to-one relationship, sometimes you'd want a URL that performs some logic; for example, a website with a logout function. The logout URL wouldn't take you to a page for logging out, but a URL that will do some logic to log you out and redirects to a homepage (logged out of your account).

```python
# website\music\urls.py
from django.urls import path, re_path
from . import views

app_name : str = 'music'  # this is the namespace for the Music app.

urlpatterns = [
    re_path(r'^$', views.index, name='index'), # pattern : /music/
    # pattern : /music/album_id/
    path('<int:album_id>/', views.detail, name='detail'),
    # pattern : /music/album_id/favorite/
    path('<int:album_id>/favorite/', views.favorite, name='favorite'),
]
```

## Adding New Attributes To The Model

Allow user to favorite selected songs as input and update the Python Song table model database.

After adding new attributes to the Python class model/table

Make some changes to the "blueprint"/model/table and make the SQL file (the change file)

```cli
python manage.py makemigrations appName
```

Now apply the changes by running the SQL/change file on the database structure

```cli
python manage.py migrate
```

Any time changes are applied to the database you also need to restart the server `ctr-c` and then `python manage.py runserver`

### Code Example : Adding New Attributes To The Model

```python
# website\music\models.py
from django.db import models

class Album(models.Model):
    artist = models.CharField(max_length=250)
    album_title = models.CharField(max_length=500)
    genre = models.CharField(max_length=250)
    album_logo_url = models.CharField(max_length=1000)

    def __str__(self):
        return self.album_title + ' - ' + self.artist


class Song(models.Model):
    album = models.ForeignKey(Album, on_delete=models.CASCADE)
    file_type = models.CharField(max_length=10)
    song_title = models.CharField(max_length=250)
    is_favorite = models.BooleanField(default=False) # Added new attribute

    def __str__(self):
        return self.song_title

```
