# New [Django](Django.md) Project Template File Explanation

from : [02 - Creating a Project](02%20-%20Creating%20a%20Project.md)

Week 14.2 | Tuesday, April 04, 2023 | 03:02 AM

## Explanation of each file in parent website, "project", folder

### manage.py

- Don't touch, modify, or delete this folder
- A program that allows you to access the database and create users for website

### website/asgi.py

- Stands for "Asynchronous Server Gateway Interface"
- **Like WSGI**, ASGI describes a common interface between a Python web application and the web server.
- **Unlike WSGI**, ASGI allows multiple, asynchronous events per application

### website/settings.py

- Settings and configuration options for the entire-overall website

### website/urls.py

- The URL declarations, the table of contents, for the website
  - `path('admin/', admin.site.urls)`
    - Look at whatever URL the user requested : `'admin/'`
    - Perform some functionality : `admin.site.urls`

### website/wsgi.py

- Stands for Web-Server-Gateway-Interface (a special type of webserver)

### website/**init**.py

- Is left blank to tell Python to treat it's fodder as a package
