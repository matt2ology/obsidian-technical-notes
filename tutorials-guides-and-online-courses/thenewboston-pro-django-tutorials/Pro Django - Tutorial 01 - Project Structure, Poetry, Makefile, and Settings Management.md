---
note-type: permanent
week-created: Week 51.2
date-created: 2023-12-19
long-form-date-created: Tuesday, December 19, 2023
time-created: 10:16 AM
source: https://www.youtube.com/watch?v=DaxcmbWcdTA&list=PL6gx4Cwl9DGDYbs0jJdGefNN8eZRSwWqy&index=1&ab_channel=thenewboston
---

# Pro Django - Tutorial 01 - Project Structure, Poetry, Makefile, and Settings Management

Related : [thenewboston-pro-django-tutorials](thenewboston-pro-django-tutorials.md)

[thenewboston](../../authors-people-key-figures/thenewboston.md) likes to kick off [Django](../../4-hub-notes-🚉/Django.md) projects as simply "project"

```sh
django-admin startproject project
```

If this doesn't work...
You may need to initialize a [Python Virtual Environment (venv)](<../../3-permanent-notes-🧲/Python%20Virtual%20Environment%20(venv).md>)

> `-m` tells Python to run a module as a script

```sh
py -m pip install --upgrade pip
py -m venv .venv
.\.venv\Scripts\activate
pip install django
django-admin --version
```

but renames the actual folder, that house the "project", as the actual
name of the project effort/idea

```sh
mv project <the name of the project>
```

that way the core python config files are set to and reference the "project"
folder and the parent folder denotes the project's effort/idea.

```txt
core-tutorials
│   manage.py
│
└───project
        asgi.py
        settings.py
        urls.py
        wsgi.py
        __init__.py
```

## README: [Markdown](../../3-permanent-notes-🧲/Markdown.md) VS. [reStructuredText](../../3-permanent-notes-🧲/reStructuredText.md)

[Differences Between Markdown and reStructuredText files](../../3-permanent-notes-🧲/Differences%20Between%20Markdown%20and%20reStructuredText%20files.md)

RST files have the extension `.rst` and stands for "reStructuredText"

The difference between a [reStructuredText (RST)](../../3-permanent-notes-🧲/reStructuredText.md) file and a Markdown file
is that a RST file has benefits when writing technical documentation.

[Current spot in video](https://youtu.be/DaxcmbWcdTA?si=_RPZ7XRjbWqWdoQ-&t=381)
