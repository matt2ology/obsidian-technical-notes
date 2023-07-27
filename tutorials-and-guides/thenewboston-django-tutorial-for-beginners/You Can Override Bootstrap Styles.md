---
alias:
---
# You Can Override Bootstrap Styles

Week 16.6 | Saturday, April 22, 2023 | 05:14 PM

Related : [Bootstrap](../../Bootstrap.md) - [27 - Finishing the Navigation Menu](27%20-%20Finishing%20the%20Navigation%20Menu.md)

Order matters. You'd need to have the CND Bootstrap first and then your own style sheet after, so the styles are cascaded and prioritized top-down.

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Music</title>
    {% load static %}
    <!-- using CDN Bootstrap 3.3.7 thenewboston uses in his tutorial -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
    <link href="https://fonts.googleapis.com/css?faimily=Satisfy" rel="stylesheet">
    <link rel="stylesheet" href="{% static 'music/style.css' %}">
</head>
```
