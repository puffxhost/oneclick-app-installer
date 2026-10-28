# 🚀 OneClick App Finder

> A polished, responsive front-end demo for searching Android app package listings. It does not install software or scan APK files.

## 🔴 Live demo

[**Open the live demo**](https://htmlpreview.github.io/?https://github.com/puffxhost/oneclick-app-installer/blob/main/index.html)

The preview is served by HTMLPreview from the repository's `main` branch. Search results are provided by a third-party APK lookup API and depend on that service being available.

## ✨ Features

- 🔎 Search app packages by name with quick-search chips
- 🕘 Recent searches stored locally in your browser, with a clear-history control
- 🌗 Persistent dark/light theme toggle
- 📱 Responsive layout and accessible labels, status messages, and keyboard focus states
- ⏱️ Request timeout, cancellation of stale requests, and clear loading/offline/error states
- 🔗 HTTPS-only external download links opened in a new tab
- 🛡️ Dynamic API content is rendered as text; external images and links are validated before use
- 🚫 No account, backend, install permissions, or file upload is required

## ⚠️ Important: what this demo does and does not do

This repository currently contains a browser-based **APK discovery interface**, not a one-click installer. It searches the configured third-party API at `https://apis.davidcyriltech.my.id/download/apk` and displays the result returned by that service. The download link is hosted by the provider.

This app does **not** scan files for malware, verify an APK signature, host APK files, or install an app on a device. The previous design implied that downloads were scanned and safe; those claims have been removed because this project does not perform those checks. Always verify the app publisher and package signature before installing an APK.

### Privacy

When you search, the search term is sent to the third-party lookup API. The last five successful search terms and your theme choice are saved in your browser's local storage. This static demo has no account system or project backend.

## 🚀 Run locally

No build tools or package installation are required.

1. Clone or download this repository.
2. Open `index.html` in a modern browser.
3. Enter an app name or choose a quick-search chip.

For a local HTTP preview, run a static server from the project folder:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## 📂 Project structure

```text
index.html   Responsive app finder UI, styles, and browser-side search logic
README.md    Project overview, live demo, and setup guide
LICENSE      MIT license
```

## 🔌 API response format

The front end expects a successful JSON response with these fields:

```json
{
  "success": true,
  "apk_name": "Example app",
  "size": "42 MB",
  "version": "1.0.0",
  "description": "Optional app description",
  "thumbnail": "https://example.com/icon.png",
  "download_link": "https://example.com/download"
}
```

The `thumbnail` and `download_link` values must use HTTPS. The interface shows a helpful error if the service is unavailable, returns no match, or provides an invalid link.

## 🧩 Deployment

This is a static site and can be hosted by any static web host. Upload `index.html` to the site's document root, or configure the host to publish the repository's root directory. The live preview link above is the hosted demo for this repository.

## 🤝 Contributing

Contributions are welcome. Fork the repository, make a focused change, and open a pull request.

## 📄 License

Released under the [MIT License](LICENSE).

## 🛟 Support

- 🌐 [Puffx Host](https://puffxhost.com)
- 📧 [support@puffxhost.in](mailto:support@puffxhost.in)
- 🐛 [Report an issue](https://github.com/puffxhost/oneclick-app-installer/issues)

