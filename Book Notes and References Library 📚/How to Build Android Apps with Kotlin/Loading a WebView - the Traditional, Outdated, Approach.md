---
aliases:
note-type: permanent
date-created: "2024-02-19"
long-form-date-created: "Monday, February 19, 2024"
week-created: "Week 08.1"
time-created: "09:43 PM"
---

# Loading a WebView - the Traditional, Outdated, Approach

Created from : [Exercise 1.03 - Configuring the Android Manifest Internet Permission](Exercise%201.03%20-%20Configuring%20the%20Android%20Manifest%20Internet%20Permission.md)

Related :

- [What is the Importance of AndroidManifest.xml](../../2-literature-notes-📝/What%20is%20the%20Importance%20of%20AndroidManifest.xml.md)
- [Where is the Layout Folder and XML file activity_main](Where%20is%20the%20Layout%20Folder%20and%20XML%20file%20activity_main.md)

## The Traditional Approach

In the book, published in May 2, 2023, it describes to do the following:

Traditionally, prior to the use of Jetpack Compose, `setContentView()` is the
method to layout resource used by an activity. Arguments passed into
`setContentView()` is a layout resource ID.

1. Switch tabs to the `MainActivity` class. From the main project window, it’s
   located at `app > java > com > example > myapplication.`

```kotlin
package com.example.myapplication
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?)
    {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
```

2. Change `setContentView(R.layout.activity_main)` to `setContentView(webView)`

```kotlin
package com.example.myapplication
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.webkit.WebView
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?){
        super.onCreate(savedInstanceState)
        val webView = WebView(this)
        webView.settings.javaScriptEnabled = true
        setContentView(webView)
        webView.loadUrl("https://www.google.com")
    }
}
```

Replacing the layout file with `WebView`. The `val` keyword is a read-only
property reference. Once set it cannot be changed. JavaScript needs to be
enabled in `WebView` to execute JavaScript.

Note that in Kotlin, the language is designed to be expressive and concise.
The type inference mechanism in Kotlin is quite powerful, allowing the compiler
to often deduce the type of a variable or expression without requiring explicit
type annotations. This helps reduce boilerplate code and makes the codebase
more readable.

When you provide an explicit type for a variable or a function return type, and
it's redundant (meaning the compiler can infer it without the explicit
annotation), Kotlin considers it as unnecessary verbosity. The Kotlin
philosophy encourages developers to write code that is clear and concise
without unnecessary redundancy.
