# Django Tutorial for Beginners - 23 - Adding Forms to the Template

Week 15.6 | Saturday, April 15, 2023 | 02:11 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [06 - Database Setup](06%20-%20Database%20Setup.md) - [09 - Database API](09%20-%20Database%20API.md) - [22 - Simple Form](22%20-%20Simple%20Form.md) - [24 - Favorite View Function](24%20-%20Favorite%20View%20Function.md)

Source : [Django Tutorial for Beginners - 23 - Adding Forms to the Template](https://youtu.be/hKoNbgVWyWc) - [HTML Forms](https://www.w3schools.com/html/html_forms.asp) - [HTML `form` method Attribute](https://www.w3schools.com/tags/att_form_method.asp)

When creating a form you should have a section for an error message: missing field entry, invalid password length, etc.

```html
<!-- website\music\templates\music\detail.html -->
{% if error_message %}
<p><strong>{{ error_message }}</strong></p>
{% endif %}
```

Creating the form needs an action. The action is what URL you want to send data to.
The song ID will be received via input

In Django it's best security practice to have a `csrf_token` (cross-site request forgery token)

1. `form action` : the action of the form is the URL you want to send the data to.
   1. Know the difference between `GET` and `POST`
2. `name="song" value="{{ song.id }}` : when we pass the form data to the views function (website\music\views.py) that will handle the information
   1. `song` is the name of the variable
   2. Get the `song.id` of the song selected

```html
<!-- website\music\templates\music\detail.html -->
<form action="{% url 'music:favorite' album.id %}" method="post">
  {% csrf_token %} {% for song in album.song_set.all %}
  <input
    type="checkbox"
    id="song{{ forloop.counter }}"
    name="song"
    value="{{ song.id }}"
  />
  <label for="song{{ forloop.counter }}">
    {{ song.song_title }} {% if song.favorite %}
    <p>⭐</p>
    {% endif %} </label
  ><br />
  {% endfor %}
  <input type="submit" value="Submit Favorite" />
</form>
```
