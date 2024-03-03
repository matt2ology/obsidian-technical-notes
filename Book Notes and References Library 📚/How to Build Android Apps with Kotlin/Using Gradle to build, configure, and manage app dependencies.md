---
note-type: literature
date-created: 2024-02-19
long-form-date-created: Monday, February 19, 2024
week-created: Week 08.1
time-created: 10:53 PM
author:
---

# Using Gradle to build, configure, and manage app dependencies

Related : [What is the Gradle Build Tool](What%20is%20the%20Gradle%20Build%20Tool.md) - [What is Groovy](What%20is%20Groovy.md)

Source : [How to Build Android Apps with Kotlin Note Hub](How%20to%20Build%20Android%20Apps%20with%20Kotlin%20Note%20Hub.md)

Topics : [Android Development](../../4-hub-notes-🚉/Android%20Development.md)

In addition to the Android platform SDK and core libraries downloaded when
Android was installed, there are other underlying technologies used to configure
and build the Android project or app: a build tool called [Gradle](Gradle).

The Android build system used the Gradle build tool to set up and runs the app
in development.

Android Studio can also use Kotlin to configure builds; but, by default,
uses [Groovy](../../3-permanent-notes-🧲/Groovy.md) to function as a dependency manager where it allows one
to add libraries to their project and specify the versions.
Sorta like PIP in Python.

The files that this build and configuration information is stored in
are named `build.gradle`.

When you first create your app, there are two `build.gradle` files:

1. At the root/top level of the **project** (the default name of the app when
   it's installed on the phone is visible on Google Play)
2. Specific to your app in the app **module** folder
