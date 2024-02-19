---
author: Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal
category-tag: books
source-tag: kindle
---

# How to Build Android Apps With Kotlin

![rw-book-cover](https://m.media-amazon.com/images/I/816f9tBDLbL._SY160.jpg)

## Metadata

- Author: [[Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal]]
- Full Title: How to Build Android Apps With Kotlin
- Category: #books

## Highlights

This book uses Android Studio, with Kotlin, to create a IMDb like app, write test, and run on virtual devices. Development will be learned from structuring an app, building out the UI with fragments via Jetpack Compose, fragments, and various navigation patterns.
We will use Android's RecyclerView Class, and the library that contains it, to display large sets of data, and learn how to fetch data and images from the web.
Then we'll learn about location services, and the permissions model before working with notifications and how to persist data. Utilize Android Architecture Components (AAC) to cleanly structure code and experiment with architecture patters and the benefits of dependency injection. Co-routines and Flow API are covered for asynchronous programming.
After you'll learn how to publish the app on the Google Play Store.

> What this book covers ([Location 417](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=417))

---

On windows Android Studio Hedgehog, android-studio-2023.1.1.26, installs Intel® HAXM (Hardware Accelerated Execution Manager)
[Intel HAXM Installation Instructions on Windows](https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows)

> installs additional components, ([Location 499](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=499))

---

Example code found there 🙂

> You can download the example code files for this book from GitHub at <https://github.com/PacktPublishing/How-to-Build-Android-Apps-with-Kotlin-Second-Edition>. If there’s an update to the code, it will be updated in the GitHub repository. ([Location 507](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=507))

---

Color images download

> You can download it here: <https://packt.link/vnOCn>. ([Location 514](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=514))

---

Create first app, build user screen flows, develop UI with Fragments, and build app navigation

> Part 1: Android Foundation ([Location 563](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=563))

---

Question - what is the importance of AndroidManifest.xml?

> understand the importance of the AndroidManifest.xml ([Location 578](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=578))

---

Question - what is the Gradle build tool?

> use the Gradle build tool to configure your app and implement user interface (UI) elements from Material Design. ([Location 579](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=579))

---

Question - what is the Android application structure?

> Android application structure ([Location 594](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=594))

---

[Introduction to Kotlin (Google I/O '17)](https://www.youtube.com/watch?v=X1RVYt2QKQE&ab_channel=AndroidDevelopers)

> The programming language you will use throughout this course to create Android apps is Kotlin. Previously the standard language to create Android apps was Java. Since Google I/O 2017 (the annual Google developer conference), this has been Google’s preferred language for Android app development. ([Location 606](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=606))

---

Using Android Studio IDE platform allows one to benefit from JetBrains' vertical integration; for, JetBrains develops and maintains the Kotlin programming language, integrated all the tool-sets and pipelines for development of Kotlin with Android Studio, and Android Studio was built on top of their other IDE application IntelliJ IDEA.

> What really sets Android Studio apart from other Android development environments is that Kotlin was created by JetBrains, the company that created IntelliJ IDEA, the software Android Studio is built on. Therefore, you can benefit from established and evolving first-class support for Kotlin. ([Location 608](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=608))

---

Kotlin was developed as an alternative to Java, aiming to improve upon several of its weaknesses. It addresses issues such as verbosity, null type handling, and introduces more functional programming techniques. These enhancements aims to streamline development, reduce boilerplate code, and enhance the overall robustness and expressiveness of the language.

> Kotlin was created to address some of the shortcomings of Java in terms of verbosity, handling null types, and adding more functional programming techniques, amongst many other issues. ([Location 611](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=611))

---

When starting a new Android Studio project you can select templates for the targeted mobile platforms (e.g. Phone and Tablet, Wear OS - smart watches, Android TV, and Automotive). It's with the mobile platform's template is where the developer can select an "activity" (i.e. the app's initial page or screen.

> the Android development ecosystem. The word displayed in most of the project types is Activity. In Android, an Activity is a page or screen. ([Location 629](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=629))

---

Package name: An address ID for source code and assets in app. Best to name this as clear and descriptive and related to what the application accomplishes. This can be accomplished sub domains (e.g. com.business.shop.candyshop). The "Name" value of the app, in lower case with spaces removed, is then appended to the domain.

> Project configuration ([Location 636](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=636))

---

Android Emulator, Android SDK Build-Tools, Android SDK Platform, Android SDK Platform-Tools, Android SDK Tools, Intel x86 Emulator Accelerator (HAXM installer), SDK Patch Applier v4.

> SDK components ([Location 682](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=682))

---

Contains all the metadata of the application as an XML file.

> A typical manifest file, in general terms, is a top-level file that describes the enclosed files or other data and associated metadata that forms a group or unit. The Android manifest applies this concept to your Android app as an XML file. ([Location 787](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=787))

---

To enable internet permissions: this is made possible by configuring the Android manifest, so a WebView can be rendered onto screen.
1 - Switch tabs to the MainActivity class. From the main project window, it’s located at app | java | com | example | myapplication.
2 - Change `setContentView(R.layout.activity_main)` to `setContentView(webView)`

> The key permission that most apps require is access to the internet. This is not added by default. ([Location 815](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=815))

---

In Kotlin, the language is designed to be expressive and concise. The type inference mechanism in Kotlin is quite powerful, allowing the compiler to often deduce the type of a variable or expression without requiring explicit type annotations. This helps reduce boilerplate code and makes the codebase more readable.
When you provide an explicit type for a variable or a function return type, and it's redundant (meaning the compiler can infer it without the explicit annotation), Kotlin considers it as unnecessary verbosity. The Kotlin philosophy encourages developers to write code that is clear and concise without unnecessary redundancy.

> Kotlin has type inference, so it will infer the type if possible. So, specifying the type explicitly with val webView: WebView = WebView(this) is not necessary. ([Location 849](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=849))

---

The Android Manifest

> It lists all the components and permissions your app uses. ([Location 873](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=873))

---
