---
aliases:
note-type: permanent
date-created: "2024-02-19"
long-form-date-created: "Monday, February 19, 2024"
week-created: "Week 08.1"
time-created: "09:47 PM"
---

# Loading a WebView - the Modern JetPack Compose Approach

Created from : [Exercise 1.03 - Configuring the Android Manifest Internet Permission](Activities%20and%20Exercises/Exercise%201.03%20-%20Configuring%20the%20Android%20Manifest%20Internet%20Permission.md)

Related :

- [Android Studio New Project Configuration Empty Activity](Android%20Studio%20New%20Project%20Configuration%20Empty%20Activity.md)
- [JetPack Compose](JetPack%20Compose)
- [Loading a WebView - the Traditional, Outdated, Approach](Loading%20a%20WebView%20-%20the%20Traditional,%20Outdated,%20Approach.md)

## The Modern JetPack Compose Approach

With JetPack Compose, the [UI](../../4-hub-notes-🚉/User%20Interface.md) is
defined programmatically, and `setContent{}`is used instead of
`setContentView()`. The `setContent{}` block is where one defines the
composable function, which describes what the UI looks like and how it behaves.

As a result, `setContentView(R.layout.activity_main)` can not be replaced with
`setContentView(webView)`, for `webView` is not a layout resource ID.

Instead one should define a composable function that creates a WebView, and
call that function within their `setContent{}` block.

In JetPack Compose, one can use the `AndroidView` function to create and
configure a `WebView`.

Example:

```kotlin
AndroidView(factory = { context ->
    WebView(context).apply {
        // configure your WebView here
    }
})
```

Now in context:

```kotlin
// projectFolderName/app/src/main/java/com/example/appProjectName/MainActivity.kt
package com.example.myapplication

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.ui.Modifier
import androidx.compose.ui.tooling.preview.Preview
import com.example.myapplication.ui.theme.MyApplicationTheme

import android.webkit.WebView
import android.webkit.WebViewClient
import androidx.compose.runtime.Composable
import androidx.compose.ui.viewinterop.AndroidView

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MyApplicationTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    WebGreeting1(url = "https://www.google.com/")
                    // WebGreeting2()
                }
            }
        }
    }
}

@Composable
fun WebGreeting1(url: String) {
    AndroidView(factory = { context ->
        WebView(context).apply {
            webViewClient = WebViewClient()
            loadUrl(url)
        }
    }, update = { webView ->
        // Use this block to update the WebView when 'url' changes
        webView.loadUrl(url)
    })
}

@Composable
fun WebGreeting2() {
    val url = "https://www.google.com/"
    AndroidView(factory = {
        WebView(it).apply {
            webViewClient = WebViewClient()
            loadUrl(url)
        }
    })
}
```
