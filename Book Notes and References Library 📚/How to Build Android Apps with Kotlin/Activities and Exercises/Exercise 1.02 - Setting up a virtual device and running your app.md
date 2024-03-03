---
aliases:
note-type: permanent
date-created: "2024-02-19"
long-form-date-created: "Monday, February 19, 2024"
week-created: "Week 08.1"
time-created: "01:46 AM"
---

# Exercise 1.02 - Setting up a virtual device and running your app

Created from : [How to Build Android Apps with Kotlin Note Hub](How%20to%20Build%20Android%20Apps%20with%20Kotlin%20Note%20Hub.md)

Related : [What is the Importance of AndroidManifest.xml](What%20is%20the%20Importance%20of%20AndroidManifest.xml.md)

## Setting up a virtual device and running your app

Installing [Android Studio](Android%20Studio) the latest Android [Software Development Kit (SDK)](<Software%20Development%20Kit%20(SDK)>) components are also installed.

This includes: A base emulator - where one can configure to create a virtual
device to run Android apps.

An emulator mimics the hardware and software features and configuration of
a real device.

- **Pro of using an emulator:** one can make changes and quickly see them on
  the desktop while developing the application. The feedback cycle is often
  quicker than going though the steps of connecting a real device.

- **Con of using an emulator:** A virtual device do not have all the features
  of a real, physical, device.

One should ensure their app runs as expected on different devices, can
standardize it by targeting a specific device by downloading a device profile,
even if they don't have a real device if this is a requirement of a particular
project.

## Steps to Setting Up A Virtual Device and Running Your App On It

1. In the tool bar of [Android Studio](Android%20Studio), as of 2024-02-18, you'll see two drop-down box menu with "app" and "No Devices" (the latter may have pre-defined emulator of a device perhaps a Pixel device like "Pixel 6 API 33"). Next to the "play button" and the debug button.
   1. If you see a box "Add Configuration"
2. To create a virtual device, click on `Device manager` to open the virtual device. If not as an icon, the feature can be found in Tools drop-down menu.
3. Click the button or toolbar option to open the Device Manager window and click the Create device button
4. A selection of, Google provided, Pixel emulators can be selected.
5. Then one can select a system image (recommended to select the latest image). The `Target` column may show "Google Play" or "Google APIs" in the name.
   1. Google APIs mean that the system image comes pre-installed with Google Play Services: this allows one's app to interface with Google apps like Google Maps and Chrome instead of a plain emulator image.

## For physical devices it can be paired wirelessly via

- **QR Code:** to pair an Android 11+ device scan the QR code.
  Developer options > Wireless debugging > Pair using QR code

- **Pair using paring code:** Go to
  Developer options > Wireless debugging > Pair device with paring code
