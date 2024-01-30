# How to Build Android Apps With Kotlin

![rw-book-cover](https://m.media-amazon.com/images/I/816f9tBDLbL._SY160.jpg)

## Metadata

- Author: [[Alex Forrester, Eran Boudjnah, Alexandru Dumbravan, and Jomar Tigcal]]
- Full Title: How to Build Android Apps With Kotlin
- Category: #books

## Highlights

- installs additional components, ([Location 499](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=499))
  - Note: On windows Android Studio Hedgehog, android-studio-2023.1.1.26, installs Intel® HAXM (Hardware Accelerated Execution Manager)
    <https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows>
- You can download the example code files for this book from GitHub at <https://github.com/PacktPublishing/How-to-Build-Android-Apps-with-Kotlin-Second-Edition>. If there’s an update to the code, it will be updated in the GitHub repository. ([Location 507](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=507))
  - Note: Example code found there 🙂
- You can download it here: <https://packt.link/vnOCn>. ([Location 514](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=514))
  - Note: Color images download
- Part 1: Android Foundation ([Location 563](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=563))
  - Note: Create first app, build user screen flows, develop UI with Fragments, and build app navigation

## New highlights added December 28, 2023 at 11:41 PM

- A typical manifest file, in general terms, is a top-level file that describes the enclosed files or other data and associated metadata that forms a group or unit. The Android manifest applies this concept to your Android app as an XML file. ([Location 787](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=787))
  - Note: Contains all the metadata of the application as an XML file.

## New highlights added January 11, 2024 at 11:31 PM

- The key permission that most apps require is access to the internet. This is not added by default. ([Location 815](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=815))
  - Note: To enable internet permissions: this is made possible by configuring the Android manifest, so a WebView can be rendered onto screen.
    1 - Switch tabs to the MainActivity class. From the main project window, it’s located at app | java | com | example | myapplication.
    2 - Change `setContentView(R.layout.activity_main)` to `setContentView(webView)`
- Kotlin has type inference, so it will infer the type if possible. So, specifying the type explicitly with val webView: WebView = WebView(this) is not necessary. ([Location 849](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=849))
  - Note: In Kotlin, the language is designed to be expressive and concise. The type inference mechanism in Kotlin is quite powerful, allowing the compiler to often deduce the type of a variable or expression without requiring explicit type annotations. This helps reduce boilerplate code and makes the codebase more readable.
    When you provide an explicit type for a variable or a function return type, and it's redundant (meaning the compiler can infer it without the explicit annotation), Kotlin considers it as unnecessary verbosity. The Kotlin philosophy encourages developers to write code that is clear and concise without unnecessary redundancy.
- It lists all the components and permissions your app uses. ([Location 873](https://readwise.io/to_kindle?action=open&asin=B0BVZX4JHS&location=873))
  - Note: The Android Manifest
