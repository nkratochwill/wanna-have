# Wanna Have

A classifieds app in Kotlin and Compose Multiplatform, built as a showcase for
[willhaben](https://www.willhaben.at). The name is a straight translation
(*will haben* → *wanna have*). Had I really pursued it, it would be the better app.

> Personal side project, not affiliated with willhaben.

## What’s in it

- **One codebase, four platforms:** Android, iOS, desktop and the web (Kotlin/Wasm) share one
  Compose Multiplatform UI.
- **Adaptive navigation:** a bottom bar on phones and a navigation rail on wide screens
  (window-size classes), on a shared NavHost where every feature brings its own routes.
- **Search:** a custom Material 3 search bar that expands, collapses and toggles mic and clear
  icons as you type, plus browsable carousels with item cards (Coil 3 image loading over Ktor).
- **Sell:** a create-listing form (“Whatcha wanna sell?”) with photo, title, description and
  save-as-draft.
- **Profile:** an account screen with settings sections.
- **Design system:** light and dark Material 3 color schemes that follow the OS, edge-to-edge
  on Android, Tab/Shift+Tab focus handling on desktop.

## Status

Early prototype: the UI runs on sample data, listings aren’t saved yet and there is no backend
(the `server` module is a Ktor stub).

## Modules

```
composeApp          app entry points (Android, iOS, desktop, web)
core/designsystem   theme, navigation bar/rail, shared components
core/model          data models
feature/search      browse and search
feature/sell        create a listing
feature/profile     account
shared              platform abstractions
server              Ktor server (stub)
iosApp              Xcode project, iOS entry point
```

## Run it

| Platform | Command |
|---|---|
| Android | `./gradlew :composeApp:installDebug` |
| Desktop | `./gradlew :composeApp:run` |
| Web | `./gradlew :composeApp:wasmJsBrowserDevelopmentRun` |
| iOS | open `iosApp/iosApp.xcodeproj` in Xcode and run |

## Stack

Kotlin 2.2 · Compose Multiplatform 1.9 · Material 3 · Navigation Compose · Ktor 3.3 · Coil 3 ·
kotlinx-datetime

## On the radar

SQLDelight, SKIE, KMP-NativeCoroutines, KMPBridge, CrashKIOS
