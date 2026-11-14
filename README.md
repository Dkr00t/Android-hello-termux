🏴‍☠️ Termux-Hello

Build Android APKs directly from Termux — no Android Studio, no computer, just your Android device.

Termux-Hello is a lightweight Android project built and compiled entirely from a mobile environment using Termux.

The project demonstrates how to manually build an Android application using command-line tools, without Gradle or Android Studio.

It includes a Java-based Android activity, an Android service, XML resources and a custom APK build pipeline.

✨ Project Overview

Termux-Hello explores Android development from the command line.

The project uses a manual build process to handle:

- Android resource compilation
- Resource linking and "R.java" generation
- Java source compilation
- DEX conversion
- APK packaging
- APK signing and verification

🛠️ Requirements

- An Android device
- "Termux" (https://f-droid.org/en/packages/com.termux/)
- OpenJDK installed in Termux
- Android SDK platform JAR ("android.jar")
- Android build tools:
  - "aapt2"
  - "dx"
  - "zip"
  - "apksigner"

⚙️ Build Environment

The project uses the following paths:

- Android SDK JAR: "~/android-sdk/android.jar"
- Java source: "src/com/example/hello/"
- Resources: "res/"
- Build directory: "build/"
- Output APK: "build/apk/app.apk"
- Final APK destination: "~/site/app.apk"

🚀 Building the APK

Run the build script from Termux:

bash mybuildapk.sh

The script automatically performs the following operations:

1. Cleans the previous build directory.
2. Compiles Android resources using "aapt2".
3. Links resources and generates "R.java".
4. Compiles Java source files using "javac".
5. Converts compiled classes into DEX using "dx".
6. Packages the DEX file into the APK.
7. Signs the APK using "apksigner".
8. Verifies the APK signature.
9. Copies the final APK into "~/site/".

When the process completes, the APK is available at:

~/site/app.apk

🔧 Build Pipeline

The APK compilation process consists of the following steps:

1. Resource Compilation

- Input: "res/"
- Tool: "aapt2 compile"
- Output: Compiled ".flat" resource files.

2. Resource Linking

- Tool: "aapt2 link"
- Generates:
  - Android resources
  - "R.java"

3. Java Compilation

- Tool: "javac"
- Input:
  - "MainActivity.java"
  - "ShellService.java"
  - "R.java"
- Output: ".class" files.

4. DEX Conversion

- Tool: "dx"
- Converts compiled Java classes into "classes.dex".

5. APK Packaging

- Adds "classes.dex" to the APK.

6. APK Signing

- Tool: "apksigner"
- Produces the final signed APK.

---

📁 Project Structure

Termux-Hello/

Source Code

- "src/com/example/hello/"
  - "MainActivity.java"
  - "ShellService.java"

Resources

- "res/drawable/logo.png"
- "res/layout/activity_main.xml"
- "res/values/strings.xml"

Configuration

- "AndroidManifest.xml"
- ".gitignore"
- "README.md"

📦 Main Components

- "MainActivity.java" — Main Android application activity.
- "ShellService.java" — Android service component.
- "AndroidManifest.xml" — Application configuration.
- "activity_main.xml" — Main user interface.
- "strings.xml" — Application string resources.
- "logo.png" — Application logo.

⚠️ Technical Limitations

This project uses a minimal manual build environment.

- Java 8 source and bytecode compatibility.
- Uses "dx" for DEX conversion.
- No Gradle or Maven dependency management.
- No automatic dependency resolution.
- No AndroidX or Jetpack integration.
- XML layouts instead of Jetpack Compose.
- No automatic ProGuard/R8 code shrinking or obfuscation.

🔐 APK Signing

The APK is signed using a local debug keystore:

~/.debug.keystore

This signing configuration is intended for development and testing, not production distribution.

The keystore should remain private and should never be committed to the repository.

🎯 Project Purpose

Termux-Hello demonstrates that Android development is not limited to a desktop computer.

With Termux and the right command-line tools, it is possible to build, package and sign an Android application directly from a smartphone.

No Android Studio. No Gradle. Just Termux, Java and a little bit of determination.

📜 Copyright

Copyright © 2026 D.K.

All rights reserved.

This repository is private. No permission is granted to copy, modify, redistribute or reuse the source code without the author's prior written authorization.
