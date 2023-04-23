# Django Tutorial for Beginners - 28 - Creating a Base Template

Week 16.6 | Saturday, April 22, 2023 | 05:28 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [27 - Finishing the Navigation Menu](27%20-%20Finishing%20the%20Navigation%20Menu.md)

Source : [Django Tutorial for Beginners - 28 - Creating a Base Template
](https://youtu.be/-nvoGfTD4QU) - [Django Template Tags](https://www.w3schools.com/django/django_template_tags.php#:~:text=In%20Django%20templates%2C%20you%20can,them%20in%20%7B%25%20%25%7D%20brackets.)

Reduce duplicate code.

## Base HTML

This base template HTML file allows us to keep a majority of elements the same, but allows modification of the content.

To do this within the app's template's app name folder create a file named `base.html` and will be our generic blueprint.

The parts we'd need for the blueprint/templates are:

1. HTML doctype declaration : `<!DOCTYPE html>`
2. Html lang : `<html lang="en"> .. </html>`
3. The HTML `<head>` Element : `<head> ... </head>`
   1. The HTML `<meta>` charset Attribute : `<meta charset="UTF-8">`
   2. The Title : `<title>Title</title>`
   3. The CSS and Script imports/includes/references/links
4. And all the other expected standard tags and elements to build a website

We also need items that are underneath the navigation bar and is defined by a "block variable" :

```html
<!-- website\music\templates\music\base.html -->

{% block variableName %}
<!-- Can name {% block body %} -->
{% endblock %}
```

To use the template we'd need to modify one of our views (a webpage : i.e. index.html) include the base template by extending within the target view HTML file `{% extends 'music/base.html' %}`

```html
<!-- website\music\templates\music\index.html -->

{% extends 'music/base.html' %} {% block title %}Music{% endblock %} {% block
content %}
<header>
  <h1>Music</h1>
</header>
<main>
  <h1>Albums</h1>
  {% if all_albums %}
  <ul>
    {% for album in all_albums %}
    <li>
      <a href="{% url 'music:detail' album.id %}">{{ album.album_title }}</a>
    </li>
    {% endfor %}
  </ul>
  {% else %}
  <h2>No albums are available.</h2>
  {% endif %}
</main>
{% endblock %}
```

```html
<!-- website\music\templates\music\base.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>{% block title %}MewSic{% endblock %}</title>
    {% load static %}
    <!-- using CDN Bootstrap 3.3.7 thenewboston uses in his tutorial -->
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
    />
    <link
      href="https://fonts.googleapis.com/css?faimily=Satisfy"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="{% static 'music/style.css' %}" />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
    <!-- using CDN Bootstrap 3.3.7 thenewboston uses in his tutorial -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
  </head>

  <body>
    <nav class="navbar navbar-inverse">
      <div class="container-fluid">
        <!-- header -->
        <div class="navbar-header">
          <button
            type="button"
            class="navbar-toggle collapsed"
            data-toggle="collapse"
            data-target="#topNavBar"
            aria-expanded="false"
          >
            <!-- Start of Hamburger Menu -->
            <span class="sr-only">Toggle navigation</span>
            <!-- three horizontal lines -->
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <!-- End of Hamburger Menu -->
          </button>
          <a class="navbar-brand" href="{% url 'music:index' %}">MewSic</a>
        </div>
        <!-- menu items -->
        <div class="collapse navbar-collapse" id="topNavBar">
          <ul class="nav navbar-nav">
            <li class="active">
              <a href="{% url 'music:index' %}">
                <span class="glyphicon glyphicon-cd" aria-hidden="true"></span
                >&nbsp; Albums
              </a>
            </li>
            <li class="">
              <a href="#">
                <span
                  class="glyphicon glyphicon-music"
                  aria-hidden="true"
                ></span
                >&nbsp; Songs
              </a>
            </li>
          </ul>
          <!-- search form -->
          <form
            class="navbar-form navbar-left"
            role="search"
            method="get"
            action="#"
          >
            <div class="form-group">
              <input
                type="text"
                class="form-control"
                placeholder="Search"
                name="query"
                value=""
              />
            </div>
            <button type="submit" class="btn btn-default">Search</button>
          </form>
          <!-- end of search form -->
          <!-- right side of navbar -->
          <ul class="nav navbar-nav navbar-right">
            <li class="">
              <a href="#">
                <span class="glyphicon glyphicon-plus" aria-hidden="true"></span
                >&nbsp; Add Album
              </a>
            </li>
            <li class="">
              <a href="#">
                <span class="glyphicon glyphicon-off" aria-hidden="true"></span
                >&nbsp; Logout
              </a>
            </li>
          </ul>
          <!-- end of right side of navbar -->
        </div>
      </div>
    </nav>
    {% block content %} {% endblock %}
    <aside>
      <h1>Aside</h1>
      <p>This is the aside content of the page.</p>
    </aside>
    <footer>
      <h1>Footer</h1>
      <p>This is the footer content of the page.</p>
    </footer>
  </body>
</html>
```

## base.html file location

```txt
# project-folder/website

│   db.sqlite3
│   manage.py
│
├───music                        # app's template's app name folder
│   │   admin.py
│   │   apps.py
│   │   models.py
│   │   tests.py
│   │   urls.py
│   │   views.py
│   │   __init__.py
│   │
│   ├───migrations
│   │
│   ├───static
│   │
│   └──templates
│       └───music
│               base.html        # <= Create this file
│               detail.html
│               index.html
│
└───website
        asgi.py
        settings.py
        urls.py
        wsgi.py
        __init__.py
```
