---
aliases: 
note-type: hub
tags:
  - hub
---

# Django

Related : [Python](4-hub-notes-🚉/Python.md) - [Web Development](4-hub-notes-🚉/Web%20Development.md)

Initial start to creating a Django project - create the starter files

## Create a Django Project

```txt
django-admin startproject <project_name>
```

## Run Application

Run the application in Windows cmd/PowerShell

```cmd
python manage.py runserver
```

> `ctr-c` to stop the local development server

## Create App in Project

To create a Django app page be at the root project directory (the folder that contains `manage.py`)

```cmd
python manage.py startapp AppName
```

## Activating Django Database Models

Make the changes by updating the database with apps model.

```sh
python manage.py makemigrations app_name
```

> OR shows the tables and columns created to database
>
> > `python manage.py sqlmigrate app_name 0001`

Now we have to run the SQL file to apply the changes

```powershell
python manage.py migrate
```

Any time changes are applied to the database you also need to restart the server `ctr-c` and then `python manage.py runserver`

## Database API

A special Django database API shell that will allow us to use database commands

```powershell
python manage.py shell
```

## Create Django Admin

This will create an administration of the backend (access to the database).

```term
python manage.py createsuperuser
```
