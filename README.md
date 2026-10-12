# Images for Runesmith

The official Images plugin for [Runesmith](https://github.com/RunesmithHub/Runesmith), `runesmith.images`. It opens PNG, JPEG, WebP,
GIF, BMP and ICO files in an image viewer instead of the text editor:

- the image on a checkerboard where it is transparent, with its format, its size in pixels and its file size above it;
- zoom with the wheel or <kbd>+</kbd> and <kbd>-</kbd>, **Fit** (<kbd>0</kbd>) and actual size (<kbd>1</kbd>), and drag to move a zoomed
  image;
- the new version when the file changes on disk.

[docs/images.md](docs/images.md) lists every action. **Open With** still offers the text editor for these files.

## Install

Install **Images** from Runesmith's plugin manager (**Tools › Plugins**), or from its page on the plugin hub,
https://hub.runesmith.dev. It needs Runesmith with plugin API 0.2.0 or newer.

## Capabilities

| Capability | Why |
| --- | --- |
| `filesystem` | Reads the image files you open, also outside the open folder. |

## Build

You need the .NET SDK version in `global.json`. The Runesmith packages come from the plugin hub's feed, which `nuget.config` sets up.

```sh
dotnet build plugin-images.slnx -warnaserror
dotnet format plugin-images.slnx --verify-no-changes
dotnet test --solution plugin-images.slnx
```

`dotnet build src/Runesmith.Images -t:InstallPlugin` installs your build into Runesmith's plugins folder; restart Runesmith to load it.

The viewer's tests are in `tests/Runesmith.Images.Tests`: `dotnet test --solution plugin-images.slnx`.

## Translations

The plugin's text is in English in `src/Runesmith.Images/locales/en/runesmith.images.ftl`, a [Fluent](https://projectfluent.org) file.

## License

Apache-2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
