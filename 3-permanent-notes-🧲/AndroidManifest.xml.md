---
aliases:
  - AndroidManifest
note-type: permanent
date-created: 2023-12-28
long-form-date-created: Thursday, December 28, 2023
week-created: Week 52.4
time-created: 11:29 PM
---

# AndroidManifest.xml

Related :

- [The importance of AndroidManifest.xml](../2-literature-notes-📝/The%20importance%20of%20AndroidManifest.xml.md)
- [Android Permissions Groups](Android%20Permissions%20Groups.md)

Topic : [Android Development](../4-hub-notes-🚉/Android%20Development.md)

It's an XML file that contains all the metadata of the application
(i.e. a table of contents of the app).

It's fancy configuration file for the application and details how the app should
behave/function (e.g. what the app can do depending on the given permission settings).

It is located at the root of the project's directory: `app | manifests | AndroidManifest.xml`

It lists all the components and permissions the app uses.

Starting the app from the launcher, it also provides the entry points into your app.
