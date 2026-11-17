# Yezhiyi · Bilingual Web Translator

[简体中文](README.md) · [Privacy and data](docs/privacy-en.html)

Yezhiyi is a Chrome Manifest V3 extension for bilingual webpages and PDF reading. The current source version is **1.0.3**; this is not a claim about the version approved or published in the Chrome Web Store.

## Read webpages

Click the floating button to translate or cancel the current page. Hover to open its radial menu for translation controls, PDFs, settings, and feedback; the menu stays open while the pointer travels between the button and the menu. When there is not enough room on the right, the button moves temporarily and returns when the menu closes. Dragging saves your preferred position, and the button snaps to an edge only when you release it within 256px of one.

The translation tooltip shows your actual Chrome keyboard shortcut when one is assigned and enabled. Configure it at `chrome://extensions/shortcuts`. The suggested shortcut is Ctrl+Shift+Y on Windows/Linux and Command+Shift+Y on macOS. Point at a paragraph and press Shift to translate or restore that paragraph.

Automatic translation is off by default. Once page translation starts, new visible content is translated as you scroll. New requests pause when the page is hidden and resume when you return. Canceling stops that page's session.

The interface supports English, Simplified Chinese, and Traditional Chinese. Other browser interface languages fall back to English. Set **Interface settings → Interface language** independently of the source and target languages. The target can follow the browser or use an explicit supported language.

## Choose a service

Google Translate and MyMemory require no API credentials; availability and usage limits depend on the service and network. Baidu requires an App ID, key, and a successful connection test for the current credentials. AI providers use your own OpenAI-compatible endpoint, API key, and model. Local Ollama requires a running local server and an installed model, with no API key.

Connection settings, request rate, and concurrency are managed separately for each service. Pages sharing an account share these limits. Configured does not mean verified, and higher limits do not guarantee faster translation. Provider billing and data policies apply.

## Read and edit PDFs

Open local files or authorize a direct online PDF source, up to 50 MiB per file. For login-protected files or redirects, download the file first and open it locally. The reader supports page thumbnails, zoom, rotation, passwords, original/translated/bilingual views, and translation review.

PDF parsing, OCR, in-place layout, revisions, independent drafts, and export run on your device. Starting translation sends eligible extracted text to the chosen translation service. PDF files and page images are not uploaded to that service. English and Simplified Chinese OCR models are bundled; other supported models and export fonts download on demand with integrity checks.

In-place revisions and independent editor drafts are separate. Automatic translated PDF export includes saved in-place revisions, but excludes independent draft changes. Use **Export page draft** to preserve editor changes through browser print preview and **Save as PDF**. Exports leave source bytes unchanged. Missing translations require an explicit choice to translate or retain the original; translation export supports up to 50 source pages at once.

## Glossary and reading style

Add local terminology rules, restrict them by target language, preserve source terms, or import/export JSON. The limit is 500 custom terms and 256 KiB per import. Import replaces the current list and requires saving. Built-in terms include Linux, RHCE, OpenShift, Kubernetes, and Red Hat.

Interface settings groups interface language, appearance (follow system, light, or dark), and thirteen color themes: Midnight Cyan is the default, with Minimal Gray, Luminous Blue, Forest Green, Soft Lavender, Warm Sand, Lagoon, Rose, Sunset, Mint, Amber, Cherry, and Indigo. Every theme has light and dark variants, and older theme settings still load. Display style separately controls bilingual mode and translation font, scale, color, weight, line height, and paragraph spacing.

## Installation and help

Use a store link or installation file provided by the maintainer. No verified store URL is included here. The public documentation repository does not contain the extension source or installation package.

If you have the extension source or an installation package, extract it to a separate directory, open `chrome://extensions`, enable Developer mode, and choose **Load unpacked** for the directory containing `manifest.json`. Loading the extension needs no build step or Node.js.

Report issues in the [public issue tracker](https://github.com/cherubr/yezhiyi-public/issues). Include browser/version, interface language, translation direction, selected service, and reproducible steps. Remove API keys and private document content before sharing logs or screenshots. See the [English user guide](https://cherubr.github.io/yezhiyi-public/help/en.html) for step-by-step operation and the [change log](https://github.com/cherubr/yezhiyi-public/blob/main/CHANGELOG.md) for released features.
