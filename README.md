# Uno Gallery

A collection of ready-to-use Fluent and Material code snippets to help speed up your multi-platform development.

Available on:

- [The Web with WebAssembly](https://gallery.platform.uno/)
- [iOS](https://apps.apple.com/us/app/uno-gallery/id1380984680)
- [Android](https://play.google.com/store/apps/details?id=com.nventive.uno.ui.demo)
- Windows
- macOS
- Linux (experimental)

![Screenshot](./images/Screenshot1.png)
![Screenshot](./images/Screenshot2.png)
![Screenshot](./images/Screenshot3.png)
![Screenshot](./images/Screenshot4.png)

## Try out Uno Gallery

- [Uno Gallery in the browser](https://gallery.platform.uno/) (WebAssembly)
- [Uno Gallery on Google Play](https://play.google.com/store/apps/details?id=com.nventive.uno.ui.demo) (Android)
- [Uno Gallery in the App Store](https://apps.apple.com/us/app/uno-gallery/id1380984680) (iOS)

## CI/CD Workflows

### Linux Package Publishing

The [Linux Package Publish](.github/workflows/linux-package-publish.yml) workflow automates building and packaging the Uno Gallery application for Linux.

**Triggers:**
- **Manual** — use the *Run workflow* button in the [Actions tab](../../actions/workflows/linux-package-publish.yml) (`workflow_dispatch`), optionally selecting the build configuration (Release/Debug).
- **Automatic** — runs automatically whenever a new GitHub Release is published (`release: [published]`).

**What it produces:**
- A `.tar.gz` archive (e.g. `uno-gallery-linux-x64-1.0.0.tar.gz`) containing the self-hosted application built for the `net10.0-desktop` target (Skia rendering).
- The archive is uploaded as a GitHub Actions artifact named `linux-package`.
- When triggered by a release event, the archive is also attached to the corresponding GitHub Release as a release asset.
- Build binary logs are uploaded as the `build-logs` artifact to aid debugging.

**Required secrets:** No additional secrets are required. The workflow uses the built-in `GITHUB_TOKEN` to attach the package to GitHub Releases.

**Runtime prerequisites for end users:**  
The produced package is a framework-dependent application. End users must have the [.NET 10 runtime](https://dotnet.microsoft.com/download/dotnet/10.0) installed. GTK 3 (`libgtk-3-0`) must also be present on the target Linux system for the desktop UI to render correctly.

## Acknowledgments

- [Uno Platform](https://platform.uno)
- [ShowMeTheXaml](https://github.com/Keboo/ShowMeTheXAML) for code snippets. Through [our Fork](https://github.com/unoplatform/ShowMeTheXAML)
- [WinUI](https://microsoft.github.io/microsoft-ui-xaml/)

## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
