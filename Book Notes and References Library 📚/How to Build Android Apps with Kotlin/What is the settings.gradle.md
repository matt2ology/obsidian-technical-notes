---
aliases:
note-type: permanent
date-created: 2024-03-02
long-form-date-created: Saturday, March 02, 2024
week-created: Week 09.6
time-created: 09:11 PM
---

# What is the `settings.gradle`

Related :

- [The app-level build.gradle file](The%20app-level%20build.gradle%20file.md)
- [Using Gradle to build, configure, and manage app dependencies](Using%20Gradle%20to%20build,%20configure,%20and%20manage%20app%20dependencies.md)
- [What are feature modules](What%20are%20feature%20modules)
- [What is the purpose of RepositoriesMode.FAIL_ON_PROJECT_REPOS in the settings.gradle](What%20is%20the%20purpose%20of%20RepositoriesMode.FAIL_ON_PROJECT_REPOS%20in%20the%20settings.gradle.md)

Topics : [Android Studio](Android%20Studio)

First time opening a new project there will only be one module `app`, but when
more features are added they can be dedicated to containing the source of a
feature rather than packaging it in the main `app` module (i.e. a "feature module").

Feature modules can be supplemented with other types of modules, these shared
modules, are used by other modules, like a networking module.

This file, the `settings.gradle.kts`, contains the repositories of the plugins
and dependencies to download in separate blocks for plugins and dependencies.

The value of `RepositoriesMode.FAIL_ON_PROJECT_REPOS` ensures all dependencies
repositories are defined here (i.e. in the file `projectFolder/settings.gradle.kts`);
otherwise, a build error will be triggered.

```kotlin script
// projectFolder/settings.gradle.kts
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

rootProject.name = "Lab01"
include(":app")
```
