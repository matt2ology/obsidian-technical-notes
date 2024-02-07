---
aliases:
  - "README - thenewboston: Django Tutorials for Beginners"
note-type: readme
---

# README - [thenewboston](https://www.youtube.com/@thenewboston): [Django Tutorials for Beginners](https://www.youtube.com/playlist?list=PL6gx4Cwl9DGBlmzzFcLgDhKTTfNLfX1IK)

Deploy with AWS : [AWS Core Development Guide](aws-core-deployment-guide.pdf)

Note Hub : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md)

Related : [Django](../../4-hub-notes-🚉/Django.md) - [README - thenewboston: Pro Django Tutorials](../thenewboston-pro-django-tutorials/README.md)

Repo : <https://github.com/matt2ology/django-thenewboston>

At time of development, 2023-04-05, I'm using Python 3.11.2.

The tutorial, thenewboston, uses Python 3.4.3

## Notes

### Create a Django Project

Initial start to creating a Django project - create the starter files

```sh
django-admin startproject <project_name>
```

### Run Application

Run the application in Windows CMD/PowerShell

```sh
python manage.py runserver
```

> `ctr-c` to stop the local development server

### Create App in Project

To create a Django app page be at the root project directory (the folder that contains `manage.py`)

```sh
python manage.py startapp AppName
```

### Activating Django Database Models

Make the changes by updating the database with apps model.

```sh
python manage.py makemigrations app_name
```

> OR shows the tables and columns created to database
>
> > `python manage.py sqlmigrate app_name 0001`

Now we have to run the SQL file to apply the changes

```sh
python manage.py migrate
```

Any time changes are applied to the database you also need to restart the server `ctr-c` and then `python manage.py runserver`

### Database API

A special Django database API shell that will allow us to use database commands

```sh
python manage.py shell
```

### Create Django Admin

This will create an administration of the backend (access to the database).

```sh
python manage.py createsuperuser
```
