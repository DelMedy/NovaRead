# NovaRead

NovaRead is a local-first PDF and manga reader for Windows and Android. It remembers your reading and listening positions, organizes chapters into series, and offers offline Read Aloud voices.

## Download

| Platform | Download |
| --- | --- |
| Windows (64-bit) | [Download NovaRead for Windows](https://github.com/DelMedy/NovaRead/releases/latest/download/NovaRead-Windows.zip) |
| Android (ARM64) | [Download the small NovaRead APK](https://github.com/DelMedy/NovaRead/releases/latest/download/NovaRead-Android.apk) |

### Windows

Extract the ZIP and double-click **Launch NovaRead.cmd**. NovaRead opens in Microsoft Edge. The ZIP includes the Node.js runtime.

To update, close NovaRead and stop its local service, then extract and launch the new copy. The default library stays in the same Windows user folder.

### Android

Open the APK from Downloads to install it. Android may ask you to allow installation from the browser or file manager you used. If NovaRead is already installed, install the APK over it to keep your app settings and reading positions.

You can import your own PDFs or connect a local folder maintained by FolderSync in **Settings → Library sync**.

From 2.6.0 the initial Android app is under 20 MB. Open **Settings → Downloads** to choose English voices, Japanese VOICEVOX voices, and English comic OCR. NovaRead also prepares missing packs when you first request their feature. They stay cached on the phone and are reused across app updates. Optional voice/model data uses additional storage; it is separate from the initial APK. Japanese translation may need an additional Google language-model download once.

Install 2.6.0 over your existing app once. Later interface updates can apply inside NovaRead without replacing the APK. Native changes use a small verified patch when one is available for your installed build, followed by Android's normal installation approval. If a patch cannot be used, NovaRead falls back to the small full APK. New voice or OCR models can require larger optional downloads.

## Comic Sources

Install a NovaRead extension from **Comic Sources**, then browse series and download chapters as images. Choose **Prepare Read Aloud** for a chapter. Automatic preparation is optional under **Settings → Comic OCR** and is off by default. Every PDF also has an **Automatic cast** voice option.

Phone OCR uses compact on-device recognition, one page at a time, with limited line batches. Read Aloud becomes available as pages are prepared; playback waits for unfinished pages instead of skipping them. It pauses scanning when the app is hidden and keeps completed pages. Large optional PC AI models are not used on the phone. Full-chapter OCR time depends on the pages and device; a universal ten-second scan time has not been established.

Android comic downloads and their reading positions use private native files and SQLite. Existing web-stored comics are copied into this storage on first use, retaining the legacy copies. Books and progress are separate from optional packs and interface updates.

See the [Comic Sources guide](https://github.com/DelMedy/NovaRead/blob/main/COMIC-SOURCES.md) for the extension format and OCR languages.

## Updates and privacy

NovaRead checks GitHub for a newer release and displays an in-app notification. You can also check manually under **Settings → App updates**. Android packs and small updates are checked against a manifest signed with the app's release key; library files are kept separately. A failed interface startup rolls back to the previous interface.

GitHub hosts the app downloads. Your library and reading history stay on your devices, with optional sync to storage you choose. Release checks send a request for public version information and never include your reading data. The downloads open with an empty library.

Third-party components retain their own license notices. The Android app includes [KittenTTS](https://huggingface.co/KittenML/kitten-tts-micro-0.8) English voices and [VOICEVOX](https://github.com/VOICEVOX/voicevox_vvm) Japanese voices. Voice credits appear in the player.
