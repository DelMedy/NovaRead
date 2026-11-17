# Comic Sources

1. Open **Comic Sources** from the sidebar or select **Browse comic sources** in Manga.
2. Choose **Install extension** for the Ubunchu! sample. For another NovaRead extension, choose **Import extension** and paste its raw GitHub manifest URL.
3. Find a series and choose **Download chapter**. NovaRead keeps the chapter’s original page images on the device.
4. Open **Downloaded comics → Read chapter**. Image reading works as soon as the download completes. Select **Read Aloud** when scanning finishes.

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
