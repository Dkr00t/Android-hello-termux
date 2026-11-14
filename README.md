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
