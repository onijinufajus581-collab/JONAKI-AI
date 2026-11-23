# JONAKI AI — Termux Android Project

A small native Java Android starter for **জনাকি AI**. It includes a Bangla chat interface, Gemini API key settings, Bengali speech-recognition intent, Android Text-to-Speech, YouTube search, and vector logo resources.

## Important limitations
- This is a functional starter, not a complete JARVIS replacement.
- Gemini requires your own API key. Add it in Settings.
- Bengali TTS voice availability depends on the phone's installed speech engine.
- Voice recognition depends on an installed Android recognition service.
- YouTube search opens the YouTube app/browser; automatic playback depends on YouTube and Android behavior.
- Screen-wide taps, background wake-word listening, and advanced accessibility automation are not included.
- The API key is stored in app-private SharedPreferences. For a public production release, use a secure backend rather than shipping a client-side key.

## Build on Termux
Android SDK build tools are not consistently available natively on ARM Termux. The provided helper uses Debian through proot-distro. Android SDK tools may still have host-architecture limitations on some phones. If the build tool reports an x86_64 executable/Exec format error, use a remote Linux ARM/x86_64 build runner or a PC build environment.

1. Install Termux from a trusted source.
2. Run:
   ```bash
   pkg update -y && pkg upgrade -y
   pkg install proot-distro unzip -y
   termux-setup-storage
   ```
3. Extract this ZIP into Termux home or shared storage.
4. Run `bash termux-setup-build.sh` from the project directory.
5. Follow the printed Debian build instructions.

## Build inside Debian
The project uses Android Gradle Plugin 8.6.1, Gradle 8.7, JDK 17, compileSdk 35, minSdk 23.
Run:
```bash
bash debian-build.sh
```
The APK should be created at `app/build/outputs/apk/debug/app-debug.apk`.

## Gemini
Create a Gemini API key using Google's official AI Studio, then open the app > সেটিংস and paste the key. Do not share the key publicly.
