---
kindle-sync:
  bookId: "17221"
  title: >-
    How to Build Android Apps with Kotlin: A practical guide to developing,
    testing, and publishing your first Android apps
  author: "Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal"
  asin: B0BVZX4JHS
  lastAnnotatedDate: "2024-02-15"
  bookImageUrl: "https://m.media-amazon.com/images/I/816f9tBDLbL._SY160.jpg"
  highlightsCount: 15
---

# How to Build Android Apps with Kotlin: A practical guide to developing, testing, and publishing your first Android apps

## Metadata

- Author: [Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal](https://www.amazon.comundefined)
- ASIN: B0BVZX4JHS
- Reference: https://www.amazon.com/dp/B0BVZX4JHS
- [Kindle link](kindle://book?action=open&asin=B0BVZX4JHS)

## Highlights

> installs additional components, ^ref-6465
>
> > — location: [499](kindle://book?action=open&asin=B0BVZX4JHS&location=499)

On windows Android Studio Hedgehog, android-studio-2023.1.1.26, installs Intel® HAXM (Hardware Accelerated Execution Manager)
https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows

---

> You can download the example code files for this book from GitHub at https://github.com/PacktPublishing/How-to-Build-Android-Apps-with-Kotlin-Second-Edition. If there’s an update to the code, it will be updated in the GitHub repository. ^ref-56528
>
> > — location: [507](kindle://book?action=open&asin=B0BVZX4JHS&location=507)

Example code found there 🙂

---

> You can download it here: https://packt.link/vnOCn. ^ref-61071
>
> > — location: [514](kindle://book?action=open&asin=B0BVZX4JHS&location=514)

Color images download

---

> Part 1: Android Foundation ^ref-50083
>
> > — location: [563](kindle://book?action=open&asin=B0BVZX4JHS&location=563)

Create first app, build user screen flows, develop UI with Fragments, and build app navigation

---

> understand the importance of the AndroidManifest.xml ^ref-61228
>
> > — location: [578](kindle://book?action=open&asin=B0BVZX4JHS&location=578)

Question: what is the importance of AndroidManifest.xml?

---

> use the Gradle build tool to configure your app and implement user interface (UI) elements from Material Design. ^ref-8046
>
> > — location: [579](kindle://book?action=open&asin=B0BVZX4JHS&location=579)

Question: what is the Gradle build tool?

---

> Android application structure ^ref-31409
>
> > — location: [594](kindle://book?action=open&asin=B0BVZX4JHS&location=594)

Question: what is the Android application structure?

---

> The programming language you will use throughout this course to create Android apps is Kotlin. Previously the standard language to create Android apps was Java. Since Google I/O 2017 (the annual Google developer conference), this has been Google’s preferred language for Android app development. ^ref-46702
>
> > — location: [606](kindle://book?action=open&asin=B0BVZX4JHS&location=606)

[Introduction to Kotlin (Google I/O '17)](https://www.youtube.com/watch?v=X1RVYt2QKQE&ab_channel=AndroidDevelopers)

---

> Kotlin was created to address some of the shortcomings of Java in terms of verbosity, handling null types, and adding more functional programming techniques, amongst many other issues. ^ref-5871
>
> > — location: [611](kindle://book?action=open&asin=B0BVZX4JHS&location=611)

---

> Project configuration ^ref-35991
>
> > — location: [636](kindle://book?action=open&asin=B0BVZX4JHS&location=636)

Package name: An address ID for source code and assets in app. Best to name this as clear and descriptive and related to what the application accomplishes. This can be accomplished sub domains (e.g. com.business.shop.candyshop). The "Name" value of the app, in lower case with spaces removed, is then appended to the domain.

---

> SDK components ^ref-8621
>
> > — location: [682](kindle://book?action=open&asin=B0BVZX4JHS&location=682)

Android Emulator, Android SDK Build-Tools, Android SDK Platform, Android SDK Platform-Tools, Android SDK Tools, Intel x86 Emulator Accelerator (HAXM installer), SDK Patch Applier v4.

---

> A typical manifest file, in general terms, is a top-level file that describes the enclosed files or other data and associated metadata that forms a group or unit. The Android manifest applies this concept to your Android app as an XML file. ^ref-50559
>
> > — location: [787](kindle://book?action=open&asin=B0BVZX4JHS&location=787)

Contains all the metadata of the application as an XML file.

---

> The key permission that most apps require is access to the internet. This is not added by default. ^ref-34314
>
> > — location: [815](kindle://book?action=open&asin=B0BVZX4JHS&location=815)

To enable internet permissions: this is made possible by configuring the Android manifest, so a WebView can be rendered onto screen.

1 - Switch tabs to the MainActivity class. From the main project window, it’s located at app | java | com | example | myapplication.

2 - Change `setContentView(R.layout.activity_main)` to `setContentView(webView)`

---

> Kotlin has type inference, so it will infer the type if possible. So, specifying the type explicitly with val webView: WebView = WebView(this) is not necessary. ^ref-32971
>
> > — location: [849](kindle://book?action=open&asin=B0BVZX4JHS&location=849)

In Kotlin, the language is designed to be expressive and concise. The type inference mechanism in Kotlin is quite powerful, allowing the compiler to often deduce the type of a variable or expression without requiring explicit type annotations. This helps reduce boilerplate code and makes the codebase more readable.

When you provide an explicit type for a variable or a function return type, and it's redundant (meaning the compiler can infer it without the explicit annotation), Kotlin considers it as unnecessary verbosity. The Kotlin philosophy encourages developers to write code that is clear and concise without unnecessary redundancy.

---

> It lists all the components and permissions your app uses. ^ref-44526
>
> > — location: [873](kindle://book?action=open&asin=B0BVZX4JHS&location=873)

The Android Manifest

---
