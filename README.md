# NovaRead

NovaRead is a local-first PDF and manga reader for Windows and Android. It remembers your reading and listening positions, organizes chapters into series, and offers offline Read Aloud voices.

## Download

| Platform | Download |
| --- | --- |
| Windows (64-bit) | [Download NovaRead for Windows](https://github.com/DelMedy/NovaRead/releases/latest/download/NovaRead-Windows.zip) |
| Android | [Download the NovaRead APK](https://github.com/DelMedy/NovaRead/releases/latest/download/NovaRead-Android.apk) |

### Windows

Extract the ZIP and double-click **Launch NovaRead.cmd**. NovaRead opens in Microsoft Edge. The ZIP includes the Node.js runtime.

To update, close NovaRead and stop its local service, then extract and launch the new copy. The default library stays in the same Windows user folder.

### Android

Open the APK from Downloads to install it. Android may ask you to allow installation from the browser or file manager you used. If NovaRead is already installed, install the APK over it to keep your app settings and reading positions.

You can import your own PDFs or connect a local folder maintained by FolderSync in **Settings → Library sync**.

## Updates and privacy

NovaRead checks GitHub for a newer release and displays an in-app notification with a download button. You can also check manually under **Settings → App updates**.

GitHub hosts the app downloads. Your library and reading history stay on your devices, with optional sync to storage you choose. Release checks send a request for public version information and never include your reading data. The downloads open with an empty library.

Third-party components retain their own license notices. The Android app includes [KittenTTS](https://huggingface.co/KittenML/kitten-tts-micro-0.8) English voices and [VOICEVOX](https://github.com/VOICEVOX/voicevox_vvm) Japanese voices. Voice credits appear in the player.
