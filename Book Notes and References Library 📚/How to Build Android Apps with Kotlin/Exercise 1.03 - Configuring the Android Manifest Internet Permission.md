---
aliases:
note-type: permanent
date-created: "2024-02-19"
long-form-date-created: "Monday, February 19, 2024"
week-created: "Week 08.1"
time-created: "09:38 PM"
---

# Exercise 1.03 - Configuring the Android Manifest Internet Permission

Created from : [How to Build Android Apps with Kotlin Note Hub](How%20to%20Build%20Android%20Apps%20with%20Kotlin%20Note%20Hub.md)

Related :

- [Loading a WebView - the Modern Jetpack Compose Approach](Loading%20a%20WebView%20-%20the%20Modern%20Jetpack%20Compose%20Approach.md)
- [Loading a WebView - the Traditional, Outdated, Approach](Loading%20a%20WebView%20-%20the%20Traditional,%20Outdated,%20Approach.md)

## Configuring the Android manifest internet permission

Not added by default the main permission that most apps require is access to
the internet.

A `WebView` enables the app to show web pages. An example can be directing
users to privacy policy, terms and conditions, a web store because Google
charges too much for in-app purchase, etc.

After [creating an Android Studio project for your app](Exercise%201.01%20–%20creating%20an%20Android%20Studio%20project%20for%20your%20app.md)

If not by default one can see the **Project** view by opening the **Tool**
window by selecting `View | Tool Windows | Project`. Common displays are both
**Project** and **Android**

Try uninstalling the app from the virtual device before running up the app
again. You need to do this, as app permissions can sometimes get cached;
as a result, to access a web page may not reflect the changed code to enable
expected feature.

### Enable Internet Permissions to the AndroidManifest.xml

If you get the `net::ERR_CLEARTEXT_NOT_PERMITTED` error, this is because the
URL you are loading into WebView is not HTTPS, and non-HTTPS traffic is disabled
from API level 28, Android 9.0 Pie and above.

To fix this we add the internet permission to the manifest.

Open up the Android manifest and add the following above the `<application>` tag:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

The full Android manifest file with the permission added here: [PacktPublishing: How to Build Android Apps with Kotlin Second Edition - AndroidManifest.xml](https://github.com/PacktPublishing/How-to-Build-Android-Apps-with-Kotlin-Second-Edition/blob/master/Chapter01/Exercise1.03/app/src/main/AndroidManifest.xml)

The Android Manifest, like a ship's manifest, describes and records what data
can be stored or accessed to and from the application.
