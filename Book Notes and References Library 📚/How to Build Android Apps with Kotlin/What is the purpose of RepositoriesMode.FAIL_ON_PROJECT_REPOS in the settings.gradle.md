---
note-type: literature
date-created: 2024-03-03
long-form-date-created: Sunday, March 03, 2024
week-created: Week 09.7
time-created: 10:25 AM
author:
---

# What is the purpose of RepositoriesMode.FAIL_ON_PROJECT_REPOS in the settings.gradle

Related : [The app-level build.gradle file](The%20app-level%20build.gradle%20file.md)

Source : [Note Hub - How to Build Android Apps with Kotlin](Note%20Hub%20-%20How%20to%20Build%20Android%20Apps%20with%20Kotlin.md)

Topics : [Android Development](../../4-hub-notes-🚉/Android%20Development.md)

In the `dependencyResolutionManagement` block of the file 
(projectFolder/app/build.gradle.kts) setting the argument 
`RepositoriesMode.FAIL_ON_PROJECT_REPOS` into `repositoriesMode.set()`
ensures all dependencies repositories that are defined in in that section of code;
otherwise, a build error will be triggered.

```kotlin script
// projectFolder\app\build.gradle.kts
pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
    }
}
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}
```
