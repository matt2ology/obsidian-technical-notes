# Django Tutorial for Beginners - 7 - Creating Models

Week 14.4 | Thursday, April 06, 2023 | 10:33 PM

related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md)
source : <https://youtu.be/UpssHYl6bjA>

<!-- Takeaways and Inspirations -->

A model is a "blueprint" of how we want to store our data.

When we make models in Django we make the "blueprints" of both
the database and Python code : via python class.

Each Python class variable is a column in the database model.

Every model, or "blueprint", created has to inherit from
`models.Model`

The variables in each Python class that were made for the database model is a column - also Django makes a unique identifier primary key (or unique key).

A primary key (a unique key) is just needed whenever you have a bunch of elements and each needs a unique ID number; in contrast, a foreign key is used whenever you have a song that's part of something else (a album).

`on_delete=models.CASCADE `means that if the album is deleted, all songs associated with that album will be deleted as well (cascading delete)

![](_image-attachments/Pasted%20image%2020230407232608.png)

```python
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
