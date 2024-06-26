---
kindle-sync:
  bookId: '17221'
  title: >-
    How to Build Android Apps with Kotlin: A practical guide to developing,
    testing, and publishing your first Android apps
  author: 'Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal'
  asin: B0BVZX4JHS
  lastAnnotatedDate: '2024-03-05'
  bookImageUrl: 'https://m.media-amazon.com/images/I/816f9tBDLbL._SY160.jpg'
  highlightsCount: 22
---

# How to Build Android Apps with Kotlin: A practical guide to developing, testing, and publishing your first Android apps

## Metadata

* Author: [Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal](https://www.amazon.comundefined)
* ASIN: B0BVZX4JHS
* Reference: https://www.amazon.com/dp/B0BVZX4JHS
* [Kindle link](kindle://book?action=open&asin=B0BVZX4JHS)

## Highlights

This book uses Android Studio, with Kotlin, to create a IMDb like app, write test, and run on virtual devices. Development will be learned from structuring an app, building out the UI with fragments via Jetpack Compose, fragments, and various navigation patterns.

We will use Android's RecyclerView Class, and the library that contains it, to display large sets of data, and learn how to fetch data and images from the web. ^ref-43025

Then we'll learn about location services, and the permissions model before working with notifications and how to persist data. Utilize Android Architecture Components (AAC) to cleanly structure code and experiment with architecture patters and the benefits of dependency injection. Coroutines and Flow API are covered for asynchronous programming.

After you'll learn how to publish the app on the Google Play Store.

> What this book covers — location: [417](kindle://book?action=open&asin=B0BVZX4JHS&location=417)

---
On windows Android Studio Hedgehog, android-studio-2023.1.1.26, installs Intel® HAXM (Hardware Accelerated Execution Manager)

[Intel HAXM Installation Instructions on Windows](https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows) ^ref-6465

> installs additional components, — location: [499](kindle://book?action=open&asin=B0BVZX4JHS&location=499)

---
Example code found there 🙂

> You can download the example code files for this book from GitHub at https://github.com/PacktPublishing/How-to-Build-Android-Apps-with-Kotlin-Second-Edition. If there’s an update to the code, it will be updated in the GitHub repository. — location: [507](kindle://book?action=open&asin=B0BVZX4JHS&location=507) ^ref-56528

---
Color images download

> You can download it here: https://packt.link/vnOCn. — location: [514](kindle://book?action=open&asin=B0BVZX4JHS&location=514) ^ref-61071

---
Create first app, build user screen flows, develop UI with Fragments, and build app navigation

> Part 1: Android Foundation — location: [563](kindle://book?action=open&asin=B0BVZX4JHS&location=563) ^ref-50083

---
Question - what is the importance of AndroidManifest.xml?

> understand the importance of the AndroidManifest.xml — location: [578](kindle://book?action=open&asin=B0BVZX4JHS&location=578) ^ref-61228

---
Question - what is the Gradle build tool?

> use the Gradle build tool to configure your app and implement user interface (UI) elements from Material Design. — location: [579](kindle://book?action=open&asin=B0BVZX4JHS&location=579) ^ref-8046

---
Question - what is the Android application structure?

> Android application structure — location: [594](kindle://book?action=open&asin=B0BVZX4JHS&location=594) ^ref-31409

---
[Introduction to Kotlin (Google I/O '17)](https://www.youtube.com/watch?v=X1RVYt2QKQE&amp;ab_channel=AndroidDevelopers)

> The programming language you will use throughout this course to create Android apps is Kotlin. Previously the standard language to create Android apps was Java. Since Google I/O 2017 (the annual Google developer conference), this has been Google’s preferred language for Android app development. — location: [606](kindle://book?action=open&asin=B0BVZX4JHS&location=606) ^ref-46702

---
Using Android Studio IDE platform allows one to benefit from JetBrains' vertical integration; for, JetBrains develops and maintains the Kotlin programming language, integrated all the tool-sets and pipelines for development of Kotlin with Android Studio, and Android Studio was built on top of their other IDE application IntelliJ IDEA.

> What really sets Android Studio apart from other Android development environments is that Kotlin was created by JetBrains, the company that created IntelliJ IDEA, the software Android Studio is built on. Therefore, you can benefit from established and evolving first-class support for Kotlin. — location: [608](kindle://book?action=open&asin=B0BVZX4JHS&location=608) ^ref-10384

---
Kotlin was developed as an alternative to Java, aiming to improve upon several of its weaknesses. It addresses issues such as verbosity, null type handling, and introduces more functional programming techniques. These enhancements aims to streamline development, reduce boilerplate code, and enhance the overall robustness and expressiveness of the language.

> Kotlin was created to address some of the shortcomings of Java in terms of verbosity, handling null types, and adding more functional programming techniques, amongst many other issues. — location: [611](kindle://book?action=open&asin=B0BVZX4JHS&location=611) ^ref-5871

---
When starting a new Android Studio project you can select templates for the targeted mobile platforms (e.g. Phone and Tablet, Wear OS - smart watches, Android TV, and Automotive). It's with the mobile platform's template is where the developer can select an "activity" (i.e. the app's initial page or screen.

> the Android development ecosystem. The word displayed in most of the project types is Activity. In Android, an Activity is a page or screen. — location: [629](kindle://book?action=open&asin=B0BVZX4JHS&location=629) ^ref-378

---
Package name: An address ID for source code and assets in app. Best to name this as clear and descriptive and related to what the application accomplishes. This can be accomplished sub domains (e.g. com.business.shop.candyshop). The "Name" value of the app, in lower case with spaces removed, is then appended to the domain.

> Project configuration — location: [636](kindle://book?action=open&asin=B0BVZX4JHS&location=636) ^ref-35991

---
Android Emulator, Android SDK Build-Tools, Android SDK Platform, Android SDK Platform-Tools, Android SDK Tools, Intel x86 Emulator Accelerator (HAXM installer), SDK Patch Applier v4.

> SDK components — location: [682](kindle://book?action=open&asin=B0BVZX4JHS&location=682) ^ref-8621

---
Contains all the metadata of the application as an XML file.

> A typical manifest file, in general terms, is a top-level file that describes the enclosed files or other data and associated metadata that forms a group or unit. The Android manifest applies this concept to your Android app as an XML file. — location: [787](kindle://book?action=open&asin=B0BVZX4JHS&location=787) ^ref-50559

---
To enable internet permissions: this is made possible by configuring the Android manifest, so a WebView can be rendered onto screen.

1 - Switch tabs to the MainActivity class. From the main project window, it’s located at app | java | com | example | myapplication. ^ref-34314

2 - Change `setContentView(R.layout.activity_main)` to `setContentView(webView)`

> The key permission that most apps require is access to the internet. This is not added by default. — location: [815](kindle://book?action=open&asin=B0BVZX4JHS&location=815)

---
In Kotlin, the language is designed to be expressive and concise. The type inference mechanism in Kotlin is quite powerful, allowing the compiler to often deduce the type of a variable or expression without requiring explicit type annotations. This helps reduce boilerplate code and makes the codebase more readable.

When you provide an explicit type for a variable or a function return type, and it's redundant (meaning the compiler can infer it without the explicit annotation), Kotlin considers it as unnecessary verbosity. The Kotlin philosophy encourages developers to write code that is clear and concise without unnecessary redundancy. ^ref-32971

> Kotlin has type inference, so it will infer the type if possible. So, specifying the type explicitly with val webView: WebView = WebView(this) is not necessary. — location: [849](kindle://book?action=open&asin=B0BVZX4JHS&location=849)

---
The Android Manifest, like a ship's manifest, describes and records what data
can be stored or accessed to and from the application.
 ^ref-25859
> The Android Manifest can be thought of as a table of contents of your app. It lists all the components and permissions your app uses. As you have seen from starting the app from the launcher, it also provides the entry points into your app. — location: [873](kindle://book?action=open&asin=B0BVZX4JHS&location=873)

---
In addition to the Android platform SDK and core libraries downloaded when
Android was installed, there are other underlying technologies used to configure
and build the Android project or app: a build tool called Gradle. ^ref-42873

> In the course of creating this project, you have principally used the Android platform SDK. The necessary Android libraries were downloaded when you installed Android Studio. However, these are not the only libraries that are used to create your app. To configure and build your Android project or app, a build tool called Gradle is used. Gradle is a multi-purpose build tool that Android Studio uses to build your app. — location: [878](kindle://book?action=open&asin=B0BVZX4JHS&location=878)

---
> Android Studio uses Groovy, a dynamically typed Java virtual machine (JVM) language, to configure the build process and allows easy dependency management so you can add libraries to your project and specify the versions. — location: [882](kindle://book?action=open&asin=B0BVZX4JHS&location=882) ^ref-53468

---
Is where one would set up all the root project settings and can then be applied to sub-modules/projects. Gradle is plugin system and one can write their own plugin to perform a series of tasks, and plug it into their own pipeline.

> The project-level build.gradle file — location: [890](kindle://book?action=open&asin=B0BVZX4JHS&location=890) ^ref-47415

---
Material design started with Google's designers took the perspective that software UI is 
more than just bits on screen, but behaved as they were tangible object that can be 
manipulated. This notion of "material design", practically, amounts to clean, card like, ^ref-41905
UI elements one can move around like paper, bright colors, animation that gives a sense of
location in space, and consistent drop shadows. All this was applied, in 2014, with Android L
(Android Lollipop, version 5.0-5.1.1, API level 21-22)

Source:

- [The Verge: How Google designed Android L](https://www.youtube.com/watch?v=VcG7XtVOCX8&amp;ab_channel=TheVerge)
- [Google for Developers - This is material design](https://developers.googleblog.com/2014/06/this-is-material-design.html)

In 2021, with Android 12 Google announced "Material You".
Google's all-new design and it focuses on Dynamic color, motion, and widgets.

source:

- [The Verge: Android 12 preview: here's Google's radical new design](https://www.youtube.com/watch?v=NrPBGglB4x8&amp;ab_channel=TheVerge)
- [Android Open Source Project - Material You Design](https://source.android.com/docs/core/display/material)

> Material Design is a design language created by Google that adds enriched UI elements based on real-world effects such as lighting, depth, shadows, and animations. — location: [993](kindle://book?action=open&asin=B0BVZX4JHS&location=993)

---

