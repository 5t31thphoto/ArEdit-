# AR Editor

This is the browser version of the supplied See More AR editor. It runs as a static GitHub Pages site. There is no Python editor, server, database, or GitHub API requirement.

## What it does

- Create AR projects in the browser.
- Add multiple image targets.
- Add 3D model, particle, video, audio, image, and text layers.
- Edit transforms and layer-specific settings.
- Drag layer markers in the preview.
- Download a complete GitHub-ready project ZIP.
- Paste the real deployed GitHub Pages URL later and generate a QR code.

## GitHub project ZIP convention

The generated project ZIP intentionally contains `github/workflows/build.yml`, not `.github/workflows/build.yml`. This lets the separate `drop-zip.yml` extractor unpack it without relying on hidden-folder handling. After extraction, rename `github` to `.github` and commit that rename. The normal `build.yml` push trigger then deploys the project to GitHub Pages.

## Deploying this editor

The repository contains the editor and its own `github/workflows/build.yml` in the same deliberate form. Put `drop-zip.yml` into `.github/workflows/drop-zip.yml` in a new public repository, upload this archive, let it extract, rename `github` to `.github`, and commit. GitHub Pages will then host the editor.

The editor currently loads JSZip and QRCode.js from jsDelivr and the generated AR viewer loads MindAR and A-Frame from their CDNs. The editor itself has no server component.
