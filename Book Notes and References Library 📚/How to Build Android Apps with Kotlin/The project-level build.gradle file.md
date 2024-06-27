---
note-type: literature
date-created: 2024-03-02
long-form-date-created: Saturday, March 02, 2024
week-created: Week 09.6
time-created: 11:03 AM
author:
---

# The project-level `build.gradle` file

Related :

- [The app-level build.gradle file](The%20app-level%20build.gradle%20file.md)
- [Using Gradle to build, configure, and manage app dependencies](Using%20Gradle%20to%20build,%20configure,%20and%20manage%20app%20dependencies.md)

Source : [Note Hub - How to Build Android Apps with Kotlin](Note%20Hub%20-%20How%20to%20Build%20Android%20Apps%20with%20Kotlin.md)

Topics : [Android Development](../../4-hub-notes-🚉/Android%20Development.md)

The project-level `build.gradle` file is where one would set up all their root project settings,
and can be then applied to sub-modules/projects.

The Gradle is a plugin system where one can write their own plugins that performs an
operation or series of tasks, and build it into their pipeline.

For example:

The `apply false` statement enables these plugins only to sub-project/modules
(i.e. these modules are not applied to the project's root level).

- `com.android.application`: Adds support to create an Android application
- `com.android.library`: Enables sub-projects/modules to be Android libraries
- `org.jetbrains.kotlin.com`: Provides integration and language support for Kotlin in the project

```kotlin script
// projectFolder\build.gradle.kts
// Top-level build file where you can add configuration options common to all sub-projects/modules.
plugins {
    id("com.android.application") version "8.2.0" apply false
    id("org.jetbrains.kotlin.android") version "1.9.0" apply false
}
```
