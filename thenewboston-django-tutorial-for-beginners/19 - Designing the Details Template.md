# Django Tutorial for Beginners - 19 - Designing the Details Template

Week 15.5 | Friday, April 14, 2023 | 02:20 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [14 - Templates](14%20-%20Templates.md)

Source : <https://youtu.be/ECTouGZGVx0>

![](_image-attachments/Pasted%20image%2020230415103420.png)

## CSS

```css
    body {
      font-family: "Trebuchet MS", Helvetica, sans-serif;
      background: #000000;
    }

    #grid-container {
      background-color: rgba(255, 255, 255, 0);
      display: grid;
      grid-auto-columns: 1fr 2fr 10fr 1fr 1fr;
      grid-auto-rows: 1.5fr 6fr 1fr;
      grid-template-areas:
        '... header header header ...'
        '... menu    main   aside  ...'
        '... footer footer footer ...';
    }

    header {
      color: #ffffff;
      grid-area: header;
      background-color: #2e3133;
      /* Set a specific height */
      height: 100%;
      /* Position and center the image to scale nicely on all screens */
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      position: relative;
    }

    #masthead {
      display: grid;
      grid-template-columns: auto;
      grid-template-rows: auto;
    }

    #masthead>.heading {
      grid-column-start: 2;
      grid-column-end: 5;
      grid-row-start: 2;
      grid-row-end: 3;
    }

    header>h1 {
      padding: 15px;
      background-color: rgba(0, 0, 0, 0.3);
    }

    nav {
      grid-area: menu;
      background-color: #454a4c;
    }

    #menu ul {
      margin: 0%;
      padding: 0;
      list-style-type: none;
    }

    #menu a {
      /* Grey background color */
      background-color: #eee;
      /* Black text color */
      color: black;
      /* Make the links appear below each other */
      display: block;
      /* top right bottom left padding */
      padding: 5% 0% 5% 15%;
      text-align: left;
      /* Remove underline from links */
      text-decoration: none;
    }

    #menu a:hover {
      /* Dark grey background on mouse-over */
      background-color: #ccc;
    }

    #menu a.active {
      /* background-color: #af4c4c; */
      /* Add a green color to the "active/current" link */
      background-color: #ff0009;
      color: white;
    }

    main {
      background-color: #ffffff;
      grid-area: main;
      padding: 25px 15px;
    }

    .main-grid {
      background-color: #fff;
      color: #444;
      display: grid;
      grid-gap: 20px;
      /* 2 columns */
      grid-template-columns: repeat(2, [col] auto);
      /* 1 row */
      grid-template-rows: repeat(1, [row] auto);
    }

    .box {
      background-color: #444;
      color: #fff;
      border-radius: 5px;
      padding: 20px;
      font-size: 150%;
    }

    aside {
      background-color: #454a4c;
      color: #ffffff;
      grid-area: aside;
      text-align: center;
    }

    footer {
      background-color: #2e3133;
      color: #ffffff;
      grid-area: footer;
    }
```

## HTML

```html
<body>
  <div id="grid-container">
    <header id="masthead">
      <h1>Music</h1>
    </header>
    <nav id="menu">
      <ul>
        <a href="{% url 'index' %}" class="active">HOME</a>
      </ul>
    </nav>
    <main class="main-grid">
      <div class="box">
        <h1>Album Details</h1>
        <p>Genre: {{ album.genre }}</p>
        <p>Album Name: {{ album.album_title }}</p>
        <p>Artist: {{ album.artist }}</p>
        <ul>
          {% for song in album.song_set.all %}
          <li> {{ song.song_title }} </li>
          {% endfor %}
        </ul>
      </div>
      <div class="box">
        <h1>Album Cover</h1>
        {% if album.album_logo_file %}
        <img src="{{ album.album_logo_file }}" alt="Album Cover" width="300" height="300">
        {% else %}
        <img src="{{ album.album_logo_url }}" alt="Album Cover Not Found" width="300" height="300">
        {% endif %}
      </div>
    </main>
    <aside>
      <h1>Aside</h1>
      <p>This is the aside content of the page.</p>
    </aside>
    <footer>
      <h1>Footer</h1>
      <p>This is the footer content of the page.</p>
    </footer>
  </div>
</body>

</html>
```
