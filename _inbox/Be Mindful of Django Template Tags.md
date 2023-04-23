---
alias:
---
# Be Mindful of Django Template Tags

Week 16.6 | Saturday, April 22, 2023 | 09:40 PM

Related : [28 - Creating a Base Template](../thenewboston-django-tutorial-for-beginners/28%20-%20Creating%20a%20Base%20Template.md)

Topic : [Django](../Django.md)

Source : [Django Template Tags](https://www.w3schools.com/django/django_template_tags.php#:~:text=In%20Django%20templates%2C%20you%20can,them%20in%20%7B%25%20%25%7D%20brackets.)

When utilizing Django template tags what format matters

```django
<!-- WORKS ✅ -->
{% block body %}
{% endblock %}

<!-- DOES NOT WORK ❌ -->
{% block body % }
{% endblock %}
```
