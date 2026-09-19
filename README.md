# GDLauncher Flatpak

Unofficial Flatpak packaging of [GDLauncher](https://gdlauncher.com).

This is a personal project based on the packaging work from
[roziscoding's GDLauncher Flatpak repository](https://github.com/roziscoding/gdlauncher-flatpak).

It is provided **as-is**, for personal use. It is not affiliated with or
endorsed by Gorilla Devs, and there are no guarantees that it will always
work or remain maintained.

## Install

### From the Flatpak repository

Add the repository once, then install GDLauncher:

```bash
flatpak remote-add --user --if-not-exists gdlauncher https://datakraut.github.io/gdlauncher-flatpak/gdlauncher.flatpakrepo
flatpak install --user gdlauncher gg.gdl.GDLauncher
```

Updates are handled through `flatpak update`.

### From a release bundle

A standalone `GDLauncher.flatpak` bundle is available from the releases.
Install it with:

```bash
flatpak install ./GDLauncher.flatpak
```

This does not add the repository, so updates must be installed manually.

## Build

### Using native flatpak-builder

```bash
flatpak-builder --force-clean build-dir gg.gdl.GDLauncher.yml
```

### Using Flatpak Builder

```bash
flatpak run org.flatpak.Builder --force-clean build-dir gg.gdl.GDLauncher.yml
```

## Install a local build

### Using native flatpak-builder

```bash
flatpak-builder --user --install --force-clean build-dir gg.gdl.GDLauncher.yml
```

### Using Flatpak Builder

```bash
flatpak run org.flatpak.Builder --user --install --force-clean build-dir gg.gdl.GDLauncher.yml
```

## Run

```bash
flatpak run gg.gdl.GDLauncher
```

## Updates

A scheduled job checks for new GDLauncher releases roughly every two weeks (the 1st and 15th of each month) and, when there's a new version, builds and publishes it automatically.

GDLauncher ships through its own CDN with no fixed release schedule, so this cadence is intentionally relaxed. **If a new GDLauncher version is out and this package hasn't picked it up yet, [open an issue](../../issues/new) and it'll be triggered manually** — the check can be run on demand at any time.
