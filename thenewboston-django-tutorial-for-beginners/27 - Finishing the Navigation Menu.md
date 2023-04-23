# Django Tutorial for Beginners - 27 - Finishing the Navigation Menu

Week 16.2 | Tuesday, April 18, 2023 | 12:09 AM

Related : [thenewboston-django-tutorial-for-beginners](thenewboston-django-tutorial-for-beginners.md) - [26 - Navigation Menu](26%20-%20Navigation%20Menu.md) - [You Can Override Bootstrap Styles](../You%20Can%20Override%20Bootstrap%20Styles.md) - [28 - Creating a Base Template](28%20-%20Creating%20a%20Base%20Template.md)

Source : [Django Tutorial for Beginners - 27 - Finishing the Navigation Menu](https://youtu.be/9S-jM3gpMkM)

Topic : [Bootstrap](../Bootstrap.md)

## Collapsing The Hamburger Menu Button In Navigation

When we need to display the button in the navigation bar, look at `data-target="#topNavBar"` and collapse the `div` that contains the items (`<div class="collapse navbar-collapse" id="topNavBar">`). No special code or styles needed, for it's already included in Bootstrap.

Essentially If we don't have enough room to display everything

```html
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
```

That has the same `data-target="#topNavBar"`. The following items will be hidden.

```html
<!-- menu items -->
<div class="collapse navbar-collapse" id="topNavBar">
  <ul class="nav navbar-nav">
    <li class="active">
      <a href="{% url 'music:index' %}">
        <span class="glyphicon glyphicon-cd" aria-hidden="true"></span>&nbsp;
        Albums
      </a>
    </li>
    <li class="">
      <a href="#">
        <span class="glyphicon glyphicon-music" aria-hidden="true"></span>&nbsp;
        Songs
      </a>
    </li>
  </ul>
</div>
```

## Creating A Search Bar - Left

```html
<!-- search form -->
<form class="navbar-form navbar-left" role="search" method="get" action="#">
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
```

## Creating Additional Action Buttons - Right

```html
<ul class="nav navbar-nav navbar-right">
  <!-- right side of navbar -->
  <li class="">
    <a href="#">
      <span class="glyphicon glyphicon-plus" aria-hidden="true"></span>&nbsp;
      Add Album
    </a>
  </li>
  <li class="">
    <a href="#">
      <span class="glyphicon glyphicon-off" aria-hidden="true"></span>&nbsp;
      Logout
    </a>
  </li>
</ul>
<!-- end of right side of navbar -->
```
