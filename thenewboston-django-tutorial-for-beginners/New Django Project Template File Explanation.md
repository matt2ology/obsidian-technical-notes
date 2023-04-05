# New [[Django]] Project Template File Explanation

from: [[Django Tutorial for Beginners - 2 - Creating a Project]]

Week 14.2 | Tuesday, April 04, 2023 | 03:02 AM

## Explanation of each file in parent website, "project", folder

### manage.py

- Don't touch, modify, or delete this folder
- A program that allows you to access the database and create users for website

### website/asgi.py

- ???

### website/settings.py

- Settings and configuration options for the entire-overall website

### website/urls.py

- The URL declorations, the table of contents, for the website
  - `path('admin/', admin.site.urls)`
    - Look at whatever URL the user requested : `'admin/'`
    - Perform some functionality : `admin.site.urls`

### website/wsgi.py

- Stands for Web-Server-Gateway-Interface (a special type of webserver)

### website/__init__.py

- Is left blank to tell Python to treat it's foder as a package
