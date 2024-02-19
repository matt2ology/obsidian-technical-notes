---
aliases:
note-type: permanent
date-created: "2024-02-16"
long-form-date-created: "Friday, February 16, 2024"
week-created: "Week 07.5"
time-created: "01:47 AM"
---

# Android Studio New Project Configuration Empty Activity

Created from : [How to Build Android Apps with Kotlin Note Hub](../Book%20Notes%20and%20References%20Library%20📚/How%20to%20Build%20Android%20Apps%20with%20Kotlin/How%20to%20Build%20Android%20Apps%20with%20Kotlin%20Note%20Hub.md)

Related : [What is the Importance of AndroidManifest.xml](../2-literature-notes-📝/What%20is%20the%20Importance%20of%20AndroidManifest.xml.md)

#### Android Studio New Project Configuration Empty Activity

A template-driven approach will show one the core options one will need to configure for your app.

When all filed are set with desired values...

One can then see the activity has been created `MainActivity` in one tab and the layout used for the screen in the other tab (`activity_main.xml).

##### Name

Similar to the name of your Android project, this name will appear as the default name of your app when it’s installed on a phone and visible on Google Play.

##### Package name

This uses the standard reverse domain name pattern to create a name. It will be used as an address identifier for source code and assets in your app. It is best to make this name as clear and descriptive and as closely aligned with the purpose of your app as possible. Therefore, it’s probably best to change this to use one or more sub-domains (such as com.sample.shop.myshop).

##### Save Location

This is the local folder on your machine where the app will initially be stored. This can be changed in the future, so you can probably keep the default or edit it to something different (such as Users/MyUser/android/projects). The default location will vary with the operating system you are using.

By default, the project will be saved into a new folder with the name of the application with spaces removed. This results in a MyApplication project folder being created.

##### Language

Select [Kotlin](../../4-hub-notes-🚉/Kotlin%20Programming%20Language.md) for it's Google's preferred language for Android app development

##### Minimum SDK

Depending on which version of Android Studio you download, the default might be a different version. Most of Android’s new features are made backward compatible, so the app will run fine on the vast majority of older devices. However, if one would like to target newer devices, they should consider raising the minimum API level.

##### Use legacy android.support libraries

Leave this unchecked.

One will be using AndroidX libraries, which are the replacement for the support libraries that were designed to make features on newer versions of Android backward compatible with older versions, but it provides much more than this.

It also contains new Android components called Jetpack, which, as the name suggests, boosts your Android development and provide a host of rich features you will want to use in your app, thereby simplifying common operations.
