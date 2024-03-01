---
note-type: literature
date-created: 2024-02-29
long-form-date-created: Thursday, February 29, 2024
week-created: Week 09.4
time-created: 05:11 PM
author:
---

# Where is the Layout Folder and XML file `activity_main`

Related :

- [JetPack Compose](../../_inbox/JetPack%20Compose.md)
- [Loading a WebView - the Modern Jetpack Compose Approach](Loading%20a%20WebView%20-%20the%20Modern%20Jetpack%20Compose%20Approach.md)
- [Loading a WebView - the Traditional, Outdated, Approach](Loading%20a%20WebView%20-%20the%20Traditional,%20Outdated,%20Approach.md)

Source : [StackOverflow: Missing activity_main.xml in new project in Android Studio](https://stackoverflow.com/questions/76048257/missing-activity-main-xml-in-new-project-in-android-studio)

Topics :

- [Android Development](../../4-hub-notes-🚉/Android%20Development.md)
- [Android Studio](Android%20Studio)

Before the update to Android 2022.2 the traditional Android
[UI](../../4-hub-notes-🚉/User%20Interface.md) development relied on using XML
for layout designs. Modern Android UI development is built with
[JetPack Compose](../../_inbox/JetPack%20Compose.md) where
[Kotlin](../../4-hub-notes-🚉/Kotlin%20Programming%20Language.md) is used to
tell what the [UI](../../4-hub-notes-🚉/User%20Interface.md) should present
instead of how elements should be constructed in view.

This is a declarative approach versus the, classic traditional,
imperative UI approach.

> Android 2022.2 switched from the classical views concept to Jetpack Compose,
> which does not require a layout defined in XML anymore. Everything is done
> in the Kotlin code instead.
> See [the official Jetpack Compose introduction](https://developer.android.com/jetpack/compose)
> for more info.
>
> - By user: "[Torben](https://stackoverflow.com/users/398844/torben)"
>   [edited Apr 23, 2023 at 19:56](https://stackoverflow.com/posts/76048300/revisions "show all edits to this post")
