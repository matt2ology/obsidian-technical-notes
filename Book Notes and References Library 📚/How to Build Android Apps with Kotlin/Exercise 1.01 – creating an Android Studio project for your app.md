---
aliases:
note-type: permanent
date-created: "2024-02-18"
long-form-date-created: "Sunday, February 18, 2024"
week-created: "Week 07.7"
time-created: "09:06 PM"
---

# Exercise 1.01 – creating an Android Studio project for your app

Created from : [How to Build Android Apps with Kotlin Note Hub](How%20to%20Build%20Android%20Apps%20with%20Kotlin%20Note%20Hub.md)

Related :

- [Installing Android Studio Settings](Installing%20Android%20Studio%20Settings.md)
- [Exercise 1.02 - Setting up a virtual device and running your app](Exercise%201.02%20-%20Setting%20up%20a%20virtual%20device%20and%20running%20your%20app.md)

## Creating an Android Studio project for your app

This template-driven approach covers the core options one would need to
configure an app.

1. Create new project
2. A start-up prompt will display that will help the developer with the initial setup
3. The developer can then target for a particular mobile platform and select the initial Activity (i.e. the page or screen)
4. Select "Empty Activity" and click next
   1. **Name:** Will appear as the default name of the app when it's installed on the phone is visible on Google Play.
      1. **Example:** "My Application"
   2. **Package Name:** Uses the standard reverse Domain name pattern, used as an address identifier for source code and assets in app, so best to make the package name clear, descriptive, and closely aligned with the intent and purpose of the application as possible.
      1. **Example:** "com.example.myapplication"
   3. **Save location:** The local folder on machine where the application will be initially stored. Can be changed later. A new folder will be created with the name of the app (see list item 4.1).
      1. **Example:** "D:\\repo\\first-android-app-with-kotlin\\Exercise1.01"
   4. **Minimum SDK:** Dependent on the version of Android Studio one may have downloaded, they may not have the state-of-the-art Android [APIs (Application Programming Interfaces)](<../../3-permanent-notes-🧲/APIs%20(Application%20Programming%20Interfaces).md>). Using newer API levels allow the use of new features, but at the cost of end-user Android OS version compatibility with the latest and greatest features and hardware to match.
      1. **Example:** "API 33 ("Tiramisu"; Android 13.0)"
   5. **Build configuration language:** One should use Kotlin as the language to develop Android with, but at one is at liberty to as they wish. The option to do anything else is now deprecated and are now allowed the selection of:
      - `Kotlin DSL (build.gradle.kts) [Recommended]`
      - `Kotlin DSL (build.gradle.kts) + Gradle Version Catalogs`
      - `Grooby DSL (build.gradle)`
5. Once all values have been set click "Finish".

Project will be built. The activity selected (see list item 3), under the
"Package Name", will be listed as "MainActivity" in one tab and the layout used
for the screen is listed as "activity_main.xml" in another tab. Assuming fresh
installation and default view layout, the application structure folders are in
the left panel.

- Package Name -> "MainActivity"
- Layout for screen -> "activity_main.xml"

---

**(This OPTION is now DEPRECATED Not Found in "New Project" prompt)** Option - Use legacy android.support libraries: Leave this unchecked (do not mark for use). Modern Android development uses [AndroidX](AndroidX) libraries and is the replacement of the (legacy) android.support libraries since 2018 ([Migrating to AndroidX: The time is right (Android Dev Summit '19)](https://www.youtube.com/watch?v=Hyt7LR5mXLc&ab_channel=AndroidDevelopers)). Using [AndroidX](AndroidX) includes new Android components called [[JetPack]].
