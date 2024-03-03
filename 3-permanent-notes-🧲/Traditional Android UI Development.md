---
aliases:
note-type: permanent
date-created: 2024-02-29
long-form-date-created: Thursday, February 29, 2024
week-created: Week 09.4
time-created: 11:14 PM
---

# Traditional Android UI Development

Related :

- [Loading a WebView - the Modern Jetpack Compose Approach](../Book%20Notes%20and%20References%20Library%20📚/How%20to%20Build%20Android%20Apps%20with%20Kotlin/Loading%20a%20WebView%20-%20the%20Modern%20Jetpack%20Compose%20Approach.md)
- [Loading a WebView - the Traditional, Outdated, Approach](../Book%20Notes%20and%20References%20Library%20📚/How%20to%20Build%20Android%20Apps%20with%20Kotlin/Loading%20a%20WebView%20-%20the%20Traditional,%20Outdated,%20Approach.md)
- [Where is the Layout Folder and XML file activity_main](../Book%20Notes%20and%20References%20Library%20📚/How%20to%20Build%20Android%20Apps%20with%20Kotlin/Where%20is%20the%20Layout%20Folder%20and%20XML%20file%20activity_main.md)

Topics : [Android Development](../4-hub-notes-🚉/Android%20Development.md)

Prior to Android 2022.2 XML files (e.g. `app/res/layout/activity_main.xml`)
were used to build the interface design.

The first app interface, `MainActivity`, has an XML file called: `activity_main.xml`.
This is used to build the [UI](../4-hub-notes-🚉/User%20Interface.md), the layout,
for the application. By modifying the `activity_main.xml` one can add widgets
(components) like images, textboxes, buttons, and others.

The Kotlin file `MainActivity.kt` is used to then configure the application code.

First create the components then develop the functionality.

## TL;DR

Traditionally, not the modern Jetpack Compose way to write Android applications

- `activity_main.xml` is used to create the look, feel, and structure
- `MainActivity.kt` is to create the functionality for the components/widgets
