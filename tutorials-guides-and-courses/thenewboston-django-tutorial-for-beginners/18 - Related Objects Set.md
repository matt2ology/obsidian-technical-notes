# Django Tutorial for Beginners - 18 - Related Objects Set

Week 15.5 | Friday, April 14, 2023 | 12:35 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [17 - Adding Songs to our Database](17%20-%20Adding%20Songs%20to%20our%20Database.md) - [13 - Connecting to the Database](13%20-%20Connecting%20to%20the%20Database.md)

Source : [Django Tutorial for Beginners - 18 - Related Objects Set](https://youtu.be/uvafEFi2bY4)

## Related Objects Set

### Adding items into a table via the create function (the short way)

Takes all the steps into one

Reference your album object, use `.song_set.create()`, and pass in all attributes but the `.ForeignKey`

for any operations with your table in you just need the Python class/table name from the models.py file in lower case with `\_set` appended and is followed by the `.` and a particular function like : `all()` or `count()`.

```cli
python manage.py shell
```

```python
# python manage.py shell
from music.models import Album, Song
TAYLOR_SWIFT_ALBUM_RED_REFERENCE = Album.objects.get(album_title="Red")
TAYLOR_SWIFT_ALBUM_RED_REFERENCE.artist
song = Song()
song.album = TAYLOR_SWIFT_ALBUM_RED_REFERENCE
TAYLOR_SWIFT_ALBUM_RED_REFERENCE.song_set.create(song_title="I love BlackPink", file_type='mp3')
```

The create method also provides a reference to that song, so if you need to take that object and use it in you program as a variable.

```python
once = TAYLOR_SWIFT_ALBUM_RED_REFERENCE.song_set.create(song_title="I love TWICE", file_type='mp3')
# >>> once
# <Song: I love TWICE>
# >>> once.album
# <Album: Red - Taylor Swift>
# >>> once.song_title
# 'I love TWICE'
# >>> TAYLOR_SWIFT_ALBUM_RED_REFERENCE.song_set.all()
# <QuerySet [<Song: I love my boyfriend>, <Song: I love BlackPink>, <Song: I love TWICE>]>
# >>> TAYLOR_SWIFT_ALBUM_RED_REFERENCE.song_set.count()
# 3
```

### Alternate way to add items into a table (the long way)

An alternative way to add songs to albums.

In the models.py the Python Song class is associated with the Album class via the `ForeignKey` and for this reason Django knows that the Album table has a whole set of songs associated to with it.

```python
# website\music\models.py
from django.db import models

class Album(models.Model):
    artist = models.CharField(max_length=250)
    album_title = models.CharField(max_length=500)
    genre = models.CharField(max_length=250)
    album_logo = models.CharField(max_length=1000)

    def __str__(self):
        return self.album_title + ' - ' + self.artist


class Song(models.Model):
    album = models.ForeignKey(Album, on_delete=models.CASCADE)
    file_type = models.CharField(max_length=10)
    song_title = models.CharField(max_length=250)
    is_favorite = models.BooleanField(default=False)

    def __str__(self):
        return self.song_title

```

Django allows access to the songs though a `set` : lowerCaseClassName_set

```python
# python manage.py shell
from music.models import Album, Song
TAYLOR_SWIFT_ALBUM_RED_REFERENCE = Album.objects.get(pk="1")
# or get the reference by album title instead of primary key
TAYLOR_SWIFT_ALBUM_RED_REFERENCE = Album.objects.get(album_title="Red")
TAYLOR_SWIFT_ALBUM_RED_REFERENCE.artist
# > outputs : Taylor Swift
song = Song()
song.album = TAYLOR_SWIFT_ALBUM_RED_REFERENCE
song.file_type = 'mp3'
song.song_title = "I hate my boyfriend"
song.save()
# If we need to change we do the following
song.song_title = "I love my boyfriend"
song.save()
# Access to the songs trough a set and display all of them
TAYLOR_SWIFT_ALBUM_RED_REFERENCE.song_set.all()
# > outputs : <QuerySet [<Song: I love my boyfriend>]>
```
