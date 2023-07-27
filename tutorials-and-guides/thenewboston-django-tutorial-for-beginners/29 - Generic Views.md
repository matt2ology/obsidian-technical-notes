# Django Tutorial for Beginners - 29 - Generic Views

Week 16.7 | Sunday, April 23, 2023 | 12:16 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md)

Source : [Django Tutorial for Beginners - 29 - Generic Views](https://youtu.be/c3yB0_4Yd48)

When developing or visiting a website typically they have a pattern

1. Display a list of objects (like the homepage)
2. Details about one object

For example, YouTube will list a variety of videos, but on click will present the video, it's description, and comments.

For this reason Django has a way to streamline this convention.

## Generic Views

Instead of making views with functions alone... we now leverage generic views which leverages classes instead of stand-alone functions.

```python
from django.views import generic
```

The type of view we use is inherited the two thenewboston mentions are

1. the list generic view
2. the detail generic view

We then need to specify which templates we are using
