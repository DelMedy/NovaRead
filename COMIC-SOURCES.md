# Comic Sources

## Use Suwayomi and the Keiyoushi store

1. Start [Suwayomi Server](https://github.com/Suwayomi/Suwayomi-Server/releases/latest) on your PC. Use a release with Extension API v1.6 support.
2. Open **Comic Sources → Suwayomi · Keiyoushi → Connect** in NovaRead. Suwayomi’s default address on the same PC is `http://127.0.0.1:4567`.
3. Choose **Add Keiyoushi** if the store is missing, then open **Keiyoushi extensions** and install the source you want. The server runs the extension.
4. Search for a title from the top of **Home**. NovaRead searches installed comic sources and shows relevant downloaded series. Use **Search in** to choose an individual Suwayomi source or language. Open a series’ chapter list, pick the OCR language and dialogue order, and choose **Download chapter**.
5. Open a downloaded series in **My Library** or **Manga** and choose a chapter. NovaRead prepares Read Aloud automatically. The PC is needed to browse the Suwayomi catalog and download from it. Saved chapters and supported offline voices work without the server.

NovaRead checks the detected text against the page artwork before reading it aloud. It looks for speech balloons and captions and filters out likely cover titles, contents, credits, and background print. Opening a previously downloaded chapter refreshes its automatic OCR from the saved images. Reviewed transcripts supplied by a source keep their existing dialogue and cast.

If Read Aloud skips a page or misreads it, select **Rescan OCR** in the comic reader toolbar. Rescan one page with **Recover missed dialogue** to include likely lettering outside balloons, or rescan the **Entire chapter** with the standard dialogue filter. NovaRead uses the saved images and keeps previous OCR on pages where the rescan finds no dialogue.

In **Read Aloud → Audio language**, choose **Japanese · VOICEVOX** to hear Japanese while following the original text. Android includes VOICEVOX. On Windows, use **Open VOICEVOX** to start the installed engine. Windows translates dialogue locally in Microsoft Edge. The initial language model download requires an internet connection.

For Android, use the PC’s private network address from the same Wi-Fi network. Configure your Suwayomi server to listen on that LAN address and enable **Basic Auth** if you want to connect over the network. Use HTTPS for a remote server. NovaRead remembers the address and keeps Basic Auth credentials for the active connection.

## Use a NovaRead source manifest

1. Open **Comic Sources** from the sidebar to manage installed extensions.
2. Choose **Install extension** for the Ubunchu! sample. For another NovaRead extension, choose **Import extension** and paste its raw GitHub manifest URL.
3. Find a series from **Home** and choose **Download chapter**. NovaRead keeps the chapter’s original page images on the device.
4. Open the series and chapter from **My Library**. Image reading works as soon as the download completes. Select **Read Aloud** when scanning finishes.

NovaRead scans images automatically after download. English and Japanese OCR are supported in source extensions. Windows needs the matching [Windows OCR language pack](https://support.microsoft.com/windows/manage-the-language-and-keyboard-input-layout-settings-in-windows-12a10cb4-8626-9b87-0e27-0ad7e43d7853). Android includes both recognizers. An extension can also supply a reviewed transcript with speaker labels. NovaRead automatically casts those characters. OCR passages with unidentified speakers use the narrator’s voice.

Comic downloads, OCR results, and positions are kept in this device’s NovaRead profile.

## Publish a source extension

Host a UTF-8 JSON manifest on GitHub and share the `raw.githubusercontent.com` URL. Manifests describe a catalog and do not run code. Stable IDs use lowercase letters, numbers, and hyphens.

```json
{
  "format": "novaread-comics/1",
  "id": "publisher-example",
  "name": "Publisher Example",
  "credit": "Creator, publisher, and license information",
  "series": [
    {
      "id": "series-one",
      "title": "Series One",
      "language": "en",
      "direction": "ltr",
      "chapters": [
        {
          "id": "1",
          "title": "Chapter 1",
          "pages": [
            "https://raw.githubusercontent.com/example/comics/main/chapter-1/page-001.png"
          ]
        }
      ]
    }
  ]
}
```

Use `en` or `ja` for OCR and `ltr` or `rtl` for dialogue order within a row. List pages in reading order with raw GitHub PNG, JPEG, or WebP links. A chapter can have an optional `transcript` raw JSON URL in NovaRead’s classified chapter OCR format, with page regions and a dialogue queue.

Publish image links you have permission to share. The sample extension points to the [Ubunchu! translators’ upstream archive](https://github.com/ubunchu-translators/ubunchu) with the original publisher and license credits.
