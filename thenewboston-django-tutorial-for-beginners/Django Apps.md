# Django Apps

from : [03 - Creating Our First App](03%20-%20Creating%20Our%20First%20App.md)

Week 14.3 | Wednesday, April 05, 2023 | 05:09 PM

## Django Apps

Websites built with Django are composed with "Apps", an app-component, parts that "structure" the website.

To create an app be at the root project directory (the folder that contains `manage.py`)

```cmd
python manage.py startapp AppName
```

Think "Apps" as pages of the website where each app should do one thing (can be explained simply or in a single sentence):

- A forum page : `python manage.py startapp forum`
  - Go and ask questions
- A video page : `python manage.py startapp video`
  - Watch videos
- A contact page : `python manage.py startapp contact`
  - Can instant message the person
- A profile page : `python manage.py startapp profile`
  - Can view a user's profile page
- A music page : `python manage.py startapp music`
 - To play and download audio files
