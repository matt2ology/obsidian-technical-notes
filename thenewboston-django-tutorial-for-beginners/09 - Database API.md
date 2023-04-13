# Django Tutorial for Beginners - 9 - Database API

Week 14.6 | Saturday, April 08, 2023 | 10:13 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [10 - Filtering Database Results](10%20-%20Filtering%20Database%20Results.md) - [13 - Connecting to the Database](13%20-%20Connecting%20to%20the%20Database.md)

Source : https://youtu.be/uYTiPwEGKyQ

## TL;DR

When ever creating an object we can do so in one of two ways

1. Add everything in via the constructor
   1. Example : `a = Album(artist"Taylor Swift", album_tilte="Red", genre="Country",album_logo="website\album_logo_ts.png")`
2. Create a blank constructor and then add in manually via each attribute

Regardless of which approach be sure to save your work : `object.save()`

After saving you can still update a particular attribute manually.

## Database API

A special Django database API shell that will allow us to use database commands

```powershell
python manage.py shell
```

Using our example we need to import before being able to import function

```python
from music.models import Album, Song
Album.objects.all()

# this object is now in memory - passed everything in via constructor
a = Album(artist="Taylor Swift", album_title="Red", genre="Country",album_logo="website\album_logo_ts.png")

# saves the object into database
a.save()

# shows the artist : expects "Taylor Swift"
a.artist

# shows the album title : expects "Red"
a.album_title

# Auto gen from Djanog is the primary key/ID/UniqueID : expects 1
a.id
a.pk
```

Alternatively you can populate the album via each attribute assignment

```python
from music.models import Album, Song
b = Album() # blank object without any attributes
b.artist = "Myth"
b.album_title = "High School"
b.genre = "Punk"
b.Album_logo = "website\album_logo_ts.png"
b.save()
```

## Example : The App "music" `models.py`

```python
# website\music\models.py
from django.db import models

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


class Song(models.Model):
    """
    Song model that is linked to an album model via a
    foreign key relationship (one to many) and has the following attributes:
    `file_type`, `song_title`, and `is_favorite` (boolean).
    """
    # on_delete=models.CASCADE means that if the album is deleted, all songs
    # associated with that album will be deleted as well (cascading delete)
    # foreign key relationship (one to many) with Album model
    # (one album can have many songs)
    album = models.ForeignKey(Album, on_delete=models.CASCADE)
    file_type = models.CharField(max_length=10)  # mp3, wav, etc.
    song_title = models.CharField(max_length=250)
    is_favorite = models.BooleanField(default=False)

    def __str__(self):
        """This is what will be displayed in the admin page
        for each song object created in the database
        (instead of Song object (1), Song object (2), etc.)

        Returns:
            [string] -- [song title]
        """
        return self.song_title
```
