---
alias: Django Tutorial for Beginners - 6 - Database Setup
---

# Django Tutorial for Beginners - 6 - Database Setup

Week 14.4 | Thursday, April 06, 2023 | 12:20 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md)
Source : <https://youtu.be/IU3LbtbmXXI>

Django comes with a default database in form of SQL Lite : `db.sqlite3`

In `website\website\settings.py` you'll find the engine constructs the database.

Django is not limited to just SQL-lite and can use, for example, Post or MySQL in real production environments; however, it's nice that Django comes with SQL-lite for development-testing.

```python
# website\website\settings.py
# Database
# https://docs.djangoproject.com/en/4.2/ref/settings/#databases
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

Django comes with default apps and some require the use of a database, but we'd have to
first set it up.

```python
# website\website\settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.c
```

When you kick up your server `python manage.py runserver` you maybe presented with this prompt

```text
You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
```

> This means our source code/app is not in sync with our database : `db.sqlite3`

To correct this we need to run the command

```text
python manage.py migrate
```

This will "sync-up" our database. When we type `migrate` Django will go into our
`website\website\settings.py` and looks for `INSTALLED_APPS = [ ]` for each one it will go into
that app's directory and looks for which tables to work with the corresponding app.

If everything went well we should get something like this:

> Operations to perform:
> Apply all migrations: admin, auth, contenttypes, sessions
> Running migrations:
> Applying contenttypes.0001_initial... OK
> Applying auth.0001_initial... OK
> Applying admin.0001_initial... OK
> Applying admin.0002_logentry_remove_auto_add... OK
> Applying admin.0003_logentry_add_action_flag_choices... OK
> Applying contenttypes.0002_remove_content_type_name... OK
> Applying auth.0002_alter_permission_name_max_length... OK
> Applying auth.0003_alter_user_email_max_length... OK
> Applying auth.0004_alter_user_username_opts... OK
> Applying auth.0005_alter_user_last_login_null... OK
> Applying auth.0006_require_contenttypes_0002... OK
> Applying auth.0007_alter_validators_add_error_messages... OK
> Applying auth.0008_alter_user_username_max_length... OK
> Applying auth.0009_alter_user_last_name_max_length... OK
> Applying auth.0010_alter_group_name_max_length... OK
> Applying auth.0011_update_proxy_permissions... OK
> Applying auth.0012_alter_user_first_name_max_length... OK
> Applying sessions.0001_initial... OK
