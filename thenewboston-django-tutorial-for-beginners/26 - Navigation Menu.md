# Django Tutorial for Beginners - 26 - Navigation Menu

Week 16.1 | Monday, April 17, 2023 | 08:43 PM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [25 - Bootstrap and Static Files](25%20-%20Bootstrap%20and%20Static%20Files.md) - [27 - Finishing the Navigation Menu](27%20-%20Finishing%20the%20Navigation%20Menu.md)

Source : [Django Tutorial for Beginners - 26 - Navigation Menu
](https://youtu.be/HEPTgggsRgY)
Topics : [Bootstrap](../Bootstrap.md)

The benefit of using bootstrap comes with responsive web design.

## Navigation Menu Hamburger Icon

Unique to Bootstrap, to create the "Hamburger Icon" you'd need to use `<span class="icon-bar"></span>` for each of the horizontal bars in the icon.

```html
<!-- Start of Hamburger icon -->
<span class="icon-bar"></span>
<span class="icon-bar"></span>
<span class="icon-bar"></span>
<!-- End of Hamburger icon -->
```

## Navigation Menu Code Example

```html
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
    <div class="collapse navbar-collapse">
      <ul class="nav navbar-nav">
        <li class="active">
          <a href="{% url 'music:index' %}">
            <span class="glyphicon glyphicon-cd" aria-hidden="true"></span
            >&nbsp; Albums
          </a>
        </li>
        <li class="">
          <a href="#">
            <span class="glyphicon glyphicon-music" aria-hidden="true"></span
            >&nbsp; Songs
          </a>
        </li>
      </ul>
    </div>
  </div>
</nav>
```
