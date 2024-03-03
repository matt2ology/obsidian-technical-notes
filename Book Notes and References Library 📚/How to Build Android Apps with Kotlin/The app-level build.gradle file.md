---
note-type: literature
date-created: 2024-03-02
long-form-date-created: Saturday, March 02, 2024
week-created: Week 09.6
time-created: 11:34 AM
author:
---

# The app-level `build.gradle` file

Related :

- [The project-level build.gradle file](The%20project-level%20build.gradle%20file.md)
- [What is the settings.gradle](What%20is%20the%20settings.gradle.md)
- [Using Gradle to build, configure, and manage app dependencies](Using%20Gradle%20to%20build,%20configure,%20and%20manage%20app%20dependencies.md)

Source : [How to Build Android Apps with Kotlin Note Hub](How%20to%20Build%20Android%20Apps%20with%20Kotlin%20Note%20Hub.md)

Topics : [Android Development](../../4-hub-notes-🚉/Android%20Development.md)

The app-level `build.gradle` file is specific to one's project configuration.

The plugins for Android and Kotlin, detailed in the [root `build.gradle` file](The%20project-level%20build.gradle%20file.md),
are applied to the project by "ID" in the plugins lines.

The `android{}`, in the app-level `build.gradle`, block comes from the
`com.android.application` plugin and is where one would configure their
Android-specific configuration settings:

- `namespace`: Is set from the package name specified when creating the project
  and is used for generating build and resource identifiers.
- `compileSdk`: Used to define the API level the app has been compiled with.
  This denotes that the app can use all the features of specified API level
  and lower.
- `defaultConfig`: The base

  - `applicationId`: Set to the app's package and is the app identifier that is
    used on Google Play to uniquely identify the app. It can be changed to be
    different from the package name if needed.
  - `minSdk`: The minimum API level the app supports, so then filters out the
    application from being listed in the Google Play store.
  - `targetSdk`: The API level the app is intended to work and has been tested with.
  - `versionCode`: Specifies the version code of the application. Every update
    needs to be made to the app, the version code needs to be increased
    by one or more.
  - `versionName`: A user-friendly version name that usually follows semantic
    versioning (i.e. `major.minor.patch`)
  - `testInstrumentationRunner`: The test runner to use for UI test

- `buildTypes`: A release is added that configures the app to create a
  "**release**" build

  - `minifyEnabled`: If set to `true`, Android Studio will shrink the app by
    removing unused code, as well as obfuscating (i.e. to render obscure,
    unclear, unintelligible) the app. The obfuscation step changes the name of
    source code references to values like `a.b.c()`, so that one's code is less
    prone to reverse engineering and further reduces the size of the app

- `compileOptions`: The language level of the Java source code
  (`sourceCompatibility`) and byte code (`targetCompatibility`)
- `kotlinOptions`: The [JVM](../../3-permanent-notes-🧲/Java%20Virtual%20Machine.md)
  library the `Kotlin gradle` plugin should use

The `dependencies{}` block specifies the libraries the app uses on top of the
Android platform SDK (i.e. Software Development Kit)

The dependencies follow the Maven Project Model (POM) convention of `groupId`,
`artifactId`, and `versionId` separated by, a colon, '`:`' ; for example,
`androidx.appcompat:appcompat:1.6.1`.

- The `groupId` is `androidx.appcompat`
- The `artifactId` is `appcompat`
- The `versionId` is 1.6.1

The build system locates and downloads the dependencies to build the app
from the repositories block detailed in the `settings.gradle`

[What is the settings.gradle](What%20is%20the%20settings.gradle.md)

## Example of an app-level `build.gradle` file

Default configuration by selecting an "Empty" activity as of 2024-03-02

```kotlin script
// projectFolder\app\build.gradle.kts
plugins {
    id("com.android.application")
    id("org.jetbrains.kotlin.android")
}

android {
    namespace = "com.example.myapplication"
    compileSdk = 34

    defaultConfig {
        applicationId = "com.example.myapplication"
        minSdk = 33
        targetSdk = 34
        versionCode = 1
        versionName = "1.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
        vectorDrawables {
            useSupportLibrary = true
        }
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_1_8
        targetCompatibility = JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = "1.8"
    }
    buildFeatures {
        compose = true
    }
    composeOptions {
        kotlinCompilerExtensionVersion = "1.5.1"
    }
    packaging {
        resources {
            excludes += "/META-INF/{AL2.0,LGPL2.1}"
        }
    }
}

dependencies {
    // Kotlin extensions, jetpack components with features of Android Kotlin
    implementation("androidx.core:core-ktx:1.12.0")
    implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.7.0")
    implementation("androidx.activity:activity-compose:1.8.2")
    implementation(platform("androidx.compose:compose-bom:2023.08.00"))
    implementation("androidx.compose.ui:ui")
    implementation("androidx.compose.ui:ui-graphics")
    implementation("androidx.compose.ui:ui-tooling-preview")
    // Material design compoents to theme and style the app
    implementation("androidx.compose.material3:material3")
    // Standard Test library for unit tests
    testImplementation("junit:junit:4.13.2")
    // UI Test runner
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    // Library for creating Android UI Test
    androidTestImplementation("androidx.test.espresso:espresso-core:3.5.1")
    androidTestImplementation(platform("androidx.compose:compose-bom:2023.08.00"))
    androidTestImplementation("androidx.compose.ui:ui-test-junit4")
    debugImplementation("androidx.compose.ui:ui-tooling")
    debugImplementation("androidx.compose.ui:ui-test-manifest")
}
```
