---
aliases:
  - Android Permission Levels
note-type: permanent
date-created: 2023-12-28
long-form-date-created: Thursday, December 28, 2023
week-created: Week 52.4
time-created: 11:42 PM
---

# Android Permissions Groups

Related :

- [AndroidManifest.xml](../3-permanent-notes-🧲/AndroidManifest.xml.md)
- [What is the Importance of AndroidManifest.xml](../Book%20Notes%20and%20References%20Library%20📚/How%20to%20Build%20Android%20Apps%20with%20Kotlin/What%20is%20the%20Importance%20of%20AndroidManifest.xml.md)

Topic : [Android Development](../4-hub-notes-🚉/Android%20Development.md)

Since Android 6, Marshmallow (API 23), developers are to ask the user to grant permissions
at runtime.

Permissions are grouped into three different categories: normal, signature, and dangerous.

## Normal Permissions

Usually permitted without asking for the user's consent at runtime.

These include network state, Wi-Fi, the internet, and Bluetooth.

## Signature Permissions

A private channel for communication among specific apps that share a common signature.

When apps are signed using the same certificate, they can have special permissions to share
information directly with each other, but these permissions prevent other apps that aren't
signed in the same way from accessing this shared data.

## Dangerous Permissions

Is centered around the user and their privacy.

This includes their SMS (texts), access to accounts and location, and read-write to the file
system and contacts.
