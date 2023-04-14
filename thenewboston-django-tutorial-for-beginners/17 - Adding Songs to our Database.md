# Django Tutorial for Beginners - 17 - Adding Songs to our Database

Week 15.5 | Friday, April 14, 2023 | 09:43 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md)

Source : <https://youtu.be/TnU_I8DKKYQ>

Adding songs to our database would require it to be associated to a database.

Update the model

```python
# website\music\admin.py
from django.contrib import admin

# we need this so we can register the Album and Song model with the admin site
from .models import Album, Song  # Import songs

# this is how we register the Album model with the admin site so we can see it in the admin site
admin.site.register(Album)
admin.site.register(Song)        # Updated to add Song to the registery
```

Don't have to sync up with the database because you only need to when you're adding or deleting attributes from the Python table model. The attributes represents the columns in your table

```python
# website\music\models.py
class Song(models.Model):
    album = models.ForeignKey(Album, on_delete=models.CASCADE)
    file_type = models.CharField(max_length=10)
    song_title = models.CharField(max_length=250)
    is_favorite = models.BooleanField(default=False)

    def __str__(self):
        return self.song_title
```

Now we can add songs to the Song table in the database

```python
python manage.py shell
```

We need a reference to an album. Because in our Song model we see that for each song it has an attribute that points to an album : `album = models.ForeignKey(Album, on_delete=models.CASCADE)`

```python
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
```
