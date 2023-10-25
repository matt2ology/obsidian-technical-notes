# Django Tutorial for Beginners - 25 - Bootstrap and Static Files

Week 15.7 | Sunday, April 16, 2023 | 12:22 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [26 - Navigation Menu](26%20-%20Navigation%20Menu.md)

Source : [Django Tutorial for Beginners - 25 - Bootstrap and Static Files
](https://youtu.be/Dv15y5CgCyE) - [Link to static files](https://docs.djangoproject.com/en/dev/ref/templates/builtins/#std-templatetag-static) - [Bootstrap CDN Version 5.3](https://getbootstrap.com/docs/5.3/getting-started/download/#cdn-via-jsdelivr)

Topics : [Bootstrap](../../4-hub-notes-🚉/Bootstrap.md)

Including CSS into HTML templates.

Any time you'd like to include images or CSS they are referred to as "static files". This "static" and the app named subdirectory folder is not included by default by Django and is created by the programmer in the app's directory.

```txt
├───music
│   ├───migrations
│   │   └───__pycache__
│   ├───static            # Have to create directory in app yourself
│   │   └───music         # Have to create subdirectory in app yourself
│   │       └───images    # Subdirectories of static app folder can be made
│   ├───templates
│   │   └───music
│   └───__pycache__
└───website
    └───__pycache__
```

In the template HTML files to use the CSS file you'd need to load the path to the CSS static file : `{% load static %}`.

```django
<head>
  <meta charset="UTF-8">
  <title>Music:details</title>
  <!-- loads the path, but not each file in it -->
  {% load static %}
  <!-- We want to use a dynamic relative link so we use `static` pathToFile -->
  <link rel="stylesheet" href="{% static 'music/detail.css' %}">
</head>
```

`{% static 'music/detail.css' %}` is a dynamic relative link to the app's static folder

```txt
├───music
│   ├───migrations
│   │   └───__pycache__
│   ├───static            # <= {% static 'music/detail.css' %} IS A PATH TO THIS
│   │   └───music
│   │       └───images
│   ├───templates
│   │   └───music
│   └───__pycache__
└───website
    └───__pycache__
```

## CSS Frameworks Via CDN (i.e. Bootstrap/Foundation)

If you'd like to use, for example, Bootstrap you can do so via a Content Delivery Network (CDN). Instead of copying all the Bootstrap files, saved on your computer, and used in the project the files are stored in a server and can be referenced.

```HTML
<head>
  <meta charset="UTF-8">
  <title>Music:details</title>
  {% load static %}
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KK94CHFLLe+nY2dmCWGMq91rCGa5gtU4mk92HdvYe+M/SXH301p5ILy+dN9+nJOZ" crossorigin="anonymous">
  <link rel="stylesheet" href="{% static 'music/detail.css' %}">
</head>
```

```html
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <div class="navbar-header">
      <a href="{% url 'music:index' %}" class="navbar-brand">HOME</a>
    </div>
  </div>
</nav>
```
