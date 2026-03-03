# 🐍 Snake Game — Android Native

A polished Android Snake game built in Kotlin with a custom Canvas renderer, neon dark UI, D-pad controls, swipe gestures, and progressive difficulty.

---

## ✨ Features

- Custom `View`-based game engine (no third-party game framework)
- 20×30 grid, neon dark aesthetic (navy + neon green + red food)
- Animated pulsing food, snake eyes, rounded segments
- D-pad on-screen controls + swipe gestures
- Score, high score, and level display
- Progressive speed — faster every 5 points (11 levels)
- Play / Pause / Restart

---

## 🔨 Build the APK (3 options)

### Option 1 — GitHub Actions (easiest, no setup needed)

1. Create a **free GitHub account** at github.com
2. Create a new repository (any name)
3. Upload this project folder (drag & drop in the GitHub UI, or use git)
4. Go to **Actions** tab → the build runs automatically
5. When green ✅, click the run → scroll to **Artifacts** at the bottom
6. Download `SnakeGame-debug.zip` — unzip to get `app-debug.apk`

> The APK installs directly on any Android phone (enable *Install unknown apps* in Settings first).

---

### Option 2 — Android Studio (local)

**Requirements:** Android Studio Hedgehog or newer, JDK 17+

```bash
# 1. Clone / unzip this project
# 2. Open Android Studio → File → Open → select the SnakeGame folder
# 3. Wait for Gradle sync to finish (~2 min first time)
# 4. Build → Build Bundle(s)/APK(s) → Build APK(s)
# 5. APK saved to:  app/build/outputs/apk/debug/app-debug.apk
```

Or via terminal:
```bash
cd SnakeGame
chmod +x gradlew
./gradlew assembleDebug
```

---

### Option 3 — Command line (Linux/macOS)

```bash
# Requires: JDK 17, Android SDK with build-tools 34 + platform-34
export ANDROID_HOME=~/Android/Sdk
cd SnakeGame
chmod +x gradlew
./gradlew assembleDebug
# APK: app/build/outputs/apk/debug/app-debug.apk
```

---

## 📱 Install on your phone

```bash
# With adb (USB debugging enabled on phone):
adb install app/build/outputs/apk/debug/app-debug.apk

# Or just copy the APK to your phone and open it
```

---

## 📁 Project Structure

```
SnakeGame/
├── .github/workflows/build.yml   ← GitHub Actions CI
├── app/src/main/
│   ├── java/com/example/snakegame/
│   │   ├── SnakeGameView.kt      ← Game engine & renderer
│   │   └── MainActivity.kt       ← Activity + gesture/button control
│   ├── res/
│   │   ├── layout/activity_main.xml
│   │   ├── drawable/             ← Vector icons, button backgrounds
│   │   ├── mipmap-*/             ← Launcher icons
│   │   └── values/               ← Colors, strings, themes
│   └── AndroidManifest.xml
├── build.gradle
├── settings.gradle
└── gradlew / gradlew.bat
```

---

## 🎮 Controls

| Action | Method |
|--------|--------|
| Steer snake | D-pad buttons or swipe on board |
| Start game | Tap ▶ button or tap board |
| Pause/Resume | Tap ⏸ button |
| Restart | Tap ▶ after Game Over |

---

## Requirements

- **minSdk:** 24 (Android 7.0+)
- **targetSdk:** 34 (Android 14)
- **Language:** Kotlin 1.9
- **Build tools:** Gradle 8.2 + AGP 8.2
