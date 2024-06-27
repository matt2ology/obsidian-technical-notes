---
aliases:
note-type: literature
date-created: 2023-12-28
long-form-date-created: Thursday, December 28, 2023
week-created: Week 52.4
time-created: 09:59 PM
---

# What is the Importance of `AndroidManifest.xml`

Related : [[What is an Android Source Set]] - [Android Permissions Groups](../../3-permanent-notes-🧲/Android%20Permissions%20Groups.md)

Source : [Note Hub - How to Build Android Apps with Kotlin](Note%20Hub%20-%20How%20to%20Build%20Android%20Apps%20with%20Kotlin.md)

Topics : [Android Development](../../4-hub-notes-🚉/Android%20Development.md)

TL;DR : [AndroidManifest.xml](../../3-permanent-notes-🧲/AndroidManifest.xml.md)

## Notes

It sits at the root of the project's "source set".
Found in the folder path: `app | manifests | AndroidManifest.xml`

The app is driven from the `AndroidManifest.xml` file, a manifest (i.e. a list) file that
details the contents of the app; in short, it contains all the metadata of the app as an XML
file.

In Android app development, each app has an application class for configuration. The
`<application>` element is used to define app components. In the given code snippet

```xml
<activity android:name=".MainActivity">
```

an activity named "`.MainActivity`" is specified as the first screen.

The `<intent-filter>` element is used to register the app's capability to react to intents,
with `<android.intent.action.MAIN>` designating the main entry point.

The inclusion of "`Android.intent.category.LAUNCHER`" indicates that the app will appear in
the device launcher when launched by the user.

When creating an app from a template, the manifest file is configured to launch the app and
display an initial screen using an Activity component.

Additional features may require permissions categorized as `normal`, `signature`, or `dangerous`.

- **`Normal permissions`**, like accessing network state, Wi-Fi, internet, and Bluetooth, are usually granted without user consent.

- **`Signature permissions`** are shared among apps signed with the same certificate, allowing data sharing.

- **`Dangerous permissions`**, related to user privacy, such as SMS, account access, location, filesystem, and contacts, must be listed in the manifest

Starting from Android Marshmallow (API 23), runtime user consent is required for
dangerous permissions.

## Default AndroidManifest.xml Template

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyApplication"
        tools:targetApi="31">
        <activity
            android:name=".MainActivity"
            android:exported="true"
            android:label="@string/app_name"
            android:theme="@style/Theme.MyApplication">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```
