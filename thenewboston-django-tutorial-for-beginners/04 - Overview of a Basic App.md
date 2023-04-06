---
alias:
- Django Tutorial for Beginners - 4 - Overview of a Basic App
---
# Django Tutorial for Beginners - 4 - Overview of a Basic App

Week 14.3 | Wednesday, April 05, 2023 | 07:32 PM

Related note : [Django Apps](Django%20Apps.md)

When you create a new app Django will set you up with default files in the app's folder

```text
└───website                 # <- Parent project folder
    │   db.sqlite3
    │   manage.py
    │
    ├───music               # <- App created `python manage.py startapp music`
    │   │   admin.py
    │   │   apps.py
    │   │   models.py
    │   │   tests.py
    │   │   views.py
    │   │   __init__.py
    │   │
    │   └───migrations
    │           __init__.py
    │
    └───website
```

[Django App Template File Explanation](Django%20App%20Template%20File%20Explanation.md)