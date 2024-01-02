---
aliases:
note-type: permanent
date-created: 2023-12-30
long-form-date-created: Saturday, December 30, 2023
week-created: Week 52.6
time-created: 11:57 PM
---

# How to configure the Android manifest with internet permission

Related : [JetPack Compose](JetPack%20Compose) - [AndroidManifest](../3-permanent-notes-🧲/AndroidManifest.xml.md)

Topics : [Android Development](Android%20Development)

## Update Security Permission

Update the INTERNET permissions via the `AndroidManifest.xml` file.
Add the following above the `<application>` tag:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

> [!warning]
> If error `net::ERR_CLEARTEXT_NOT_PERMITTED` URL loading into WebView is not
> Secure (HTTPS). Non-HTTPS traffic is disabled from Android 9.0 Pie and higher
> (i.e. API level 28+).

> [!caution]
> If already attempt running build and still doesn't work uninstall the app
> and rebuild the app (i.e. hit the play button).

## Adding `WebView`

These are the changes needed based on the original configuration.

On the `ManActivity` class (_located at app | java | com | example | myapplication_)
you'll see the following

### `WebView` via Jetpack Compose

```kotlin
// Original Configuration
// app > java > com > example > myapplication > ManActivity.kt
// Modern Android UI toolkit: Jetpack Compose
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MyApplicationTheme {
                // surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    WebsiteGreeting()
                }
            }
        }
    }
}

@Composable
fun WebGreeting() {
    val url: String = "https://www.google.com/"
    AndroidView(factory = {
        WebView(it).apply {
            webViewClient = WebViewClient()
            loadUrl(url)
        }
    })
}
```

#### Explaining the code

```kotlin
@Composable
fun WebGreeting() {
    val url: String = "https://www.google.com/"
    AndroidView(factory = {
        WebView(it).apply {
            webViewClient = WebViewClient()
            loadUrl(url)
        }
    })
}
```

- `AndroidView`: A Compose function that allows to embed Android Views in a
  Compose UI
- `factory`: A lambda expression that takes "Context" as a parameter and
  returns the Android view to be embedded.
  - In this case, `factory` returns a "WebView" instance
- `WebView(it)`: Creates a new WebView where `it` is the provided "Context"
- `.apply`: Enables one to perform additional configuration on the WebView

### Original Configuration - Jetpack Compose

Jetpack Compose, a modern Android UI toolkit that simplifies and accelerates UI development. The UI is defined programmatically using composable functions and
the Compose framework. There's no XML layout file, and the UI is built using a declarative syntax.

```kotlin
// Original Configuration
// app > java > com > example > myapplication > ManActivity.kt
// Modern Android UI toolkit: Jetpack Compose
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MyApplicationTheme {
                // surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    Greeting("Android")
                }
            }
        }
    }
}

@Composable
fun Greeting(name: String, modifier: Modifier = Modifier) {
    Text(
        text = "Hello $name!",
        modifier = modifier
    )
}

@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    MyApplicationTheme {
        Greeting("Android")
    }
}
```

### `WebView` via "View-based" Development: Android View system and the Android XML layout file

The `val` keyword is a read-only property reference, which cannot be changed
once set.

JavaScript needs to be enabled in WebView to execute JavaScript

```kotlin
package com.example.myapplication
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.webkit.WebView
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?){
        super.onCreate(savedInstanceState)
        // setContentView(R.layout.activity_main) <- Replaced
        val webView = WebView(this)
        webView.settings.javaScriptEnabled = true
        setContentView(webView)
        webView.loadUrl("https://www.google.com")
    }
}
```

### Original Configuration - "View-based" Development: Android View system and the Android XML layout file

The traditional Android View system and the Android XML layout file
(`activity_main.xml`). This type of Android development is often referred to as
"View-based" development.

```kotlin
// app > java > com > example > myapplication > ManActivity.kt
// Original Configuration
// "View-based" development
// Traditional Android View system and the Android XML
package com.example.myapplication
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?)
    {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}
```
