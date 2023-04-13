# [Django](../Django.md) App Template File Explanation

Week 14.3 | Wednesday, April 05, 2023 | 09:18 PM

From : [04 - Overview of a Basic App](04%20-%20Overview%20of%20a%20Basic%20App.md)
Related : [Django Project Template File Explanation](Django%20Project%20Template%20File%20Explanation.md) - [\_\_init\_\_.py](__init__.py.md)

## New Django App Template File Explanation

### migrations folder

A way to connect/hook-up website/source code with Database

Practically a one liner in Django

### admin.py

Django development team knew that a large majority of websites has an admin page.
A section that allows a particular user to create users, delete posts, ect.

So instead of making it yourself the Django dev team included this function natively.

### apps.py

This file is the configuration file of the app created

### models.py

A model is the blueprint for the database.
How we are going to store data for the app.

The tables in the database.

### tests.py

Create tests.

### views.py

Python functions that take user request and responds with a particular action.
