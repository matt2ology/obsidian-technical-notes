# Django Tutorial for Beginners - 14 - Templates

Week 15.3 | Wednesday, April 12, 2023 | 07:46 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [13 - Connecting to the Database](13%20-%20Connecting%20to%20the%20Database.md) - [Special syntax when using Django in an HTML document](Special%20syntax%20when%20using%20Django%20in%20an%20HTML%20document.md)

Source : <https://youtu.be/0HVwUQ0Ok7Y>

GitHub permalink : [<!DOCTYPE html>](https://github.com/matt2ology/django-thenewboston/blob/2c6a54c3168c430dd57c4af39cf988b05d9ec20a/website/music/templates/music/index.html#L1-L22) - [def index_old_long_way(request: any) -> HttpResponse:](https://github.com/matt2ology/django-thenewboston/blob/c612ad1439f30c48dcc4300ec202f6ad38515d40/website/music/views.py#L6-L24)

## Templates - TL;DR

1. Take a template and load it in
    1. `TEMPLATE: object = loader.get_template('music/index.html')`
2. Render the template
    1. `return HttpResponse(TEMPLATE.render(CONTEXT, request))`
    2. Renders Django items and converts it into regular plain HTML

## Templates

Separating HTML code from backend Python code.

To make templates from Django you'd need to import `from django.template import loader`
Make a folder for templates in the app with a subdirectory of the same name of the app.

```txt
├───music                # music app
│   ├───migrations
│   │   └───__pycache__
│   ├───templates
│   │   └───music        # subdirectory with same name as the app
│   └───__pycache__
└───website
    └───__pycache__
```

We don't have to specify it's within the "templates/music/index.html" folder because Django (`from django.template import loader`), by default, is set up to look in the app directory "templates"

```python
# website\music\views.py
# So we can use the template in the HttpResponse object.
TEMPLATE: object = loader.get_template('music/index.html')
```

Create a Python dictionary `CONTEXT` (information our template needs) when we need to pass a table information (i.e. Album information) into our template (index.html) we pass it though a dictionary.

In the Python dictionary `CONTEXT` you can keep the name-value pairs the same name as the python code.

```python
# website\music\views.py
CONTEXT: dict = {
    'all_albums': ALL_ALBUMS,
}
```

When we have a view we need to return something

```python
# website\music\views.py
# In TEMPLATE.render(CONTEXT, request) we always pass in the request
return HttpResponse(TEMPLATE.render(CONTEXT, request))
```

Now we need to pass in the information into the template.

## Special syntax when using Django in an HTML document

-   When you need to use Python code you enclose your statements in `{% <CODE> %}`
-   When using plain variables, values that can be placed "as-is", you use `{{ }}`

Think on behalf of the user in the event there is nothing populated in the database have conditionals, so to have text on screen that the data is empty

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Music</title>
  </head>

  <body>
    <h1>Music</h1>
    {% if all_albums %}
    <ul>
      {% for album in all_albums %}
      <li><a href="{% url 'detail' album.id %}">{{ album.album_title }}</a></li>
      {% endfor %}
    </ul>
    {% else %}
    <h2>No albums are available.</h2>
    {% endif %}
  </body>
</html>
```
