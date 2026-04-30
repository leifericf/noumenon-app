# Noumenon App

Desktop app for [Noumenon](https://github.com/leifericf/noumenon). Electron + ClojureScript (Replicant). Companion to the `noum` CLI.

## Install

The app is auto-installed by `noum ui` from the [latest release](https://github.com/leifericf/noumenon-app/releases). Most users do not interact with this repo directly.

To install manually, download the platform-specific bundle from the releases page and run it.

## Develop

```bash
npm install
npx shadow-cljs watch app    # ClojureScript live-reload
npm run electron             # launch the desktop app
```

The app expects a running Noumenon daemon. Start one in a separate terminal:

```bash
noum daemon
```

Then either run `npm run electron` here, or in a sibling `noumenon` checkout, set `NOUMENON_APP_ROOT=/path/to/noumenon-app` and run `noum ui`.

## Release

Tag `vX.Y.Z` and push. The release workflow runs `electron-builder build --publish always`, which uploads DMG (macOS) and AppImage (Linux) artifacts to this repo's GitHub releases. The `noum` CLI's `electron-updater` channel reads from this repo.

## License

MIT.
