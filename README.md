# keskos-browsers-meta

`keskos-browsers-meta` is the browser bundle and browser-asset helper package group for KeskOS.

## What this is

This repository builds a pacman meta package. The package itself is empty at runtime and exists only to pull in a curated group of packages through dependencies.

## Role in KeskOS

Meta package for browser selection.

## Package name

```txt
Package: keskos-browsers-meta
Repo: [keskos]
Architecture: any
```

## What it installs or provides

- Installs no runtime files beyond pacman metadata.
- Pulls in its software set entirely through `depends` (and optional `optdepends` where present).

## Commands and launchers

- This package does not install commands, GUI launchers, config files, logs, or systemd units directly.

## Config, logs, and state

- Configuration and logs belong to the packages pulled in by this meta package, not to the meta package itself.

## Dependencies

- Current hard dependencies: `firefox` and `keskos-browser-startpage`.
- Current optional dependencies: `librewolf`, `librewolf-bin`, `zen-browser`, `zen-browser-bin`, `brave-browser`, `brave-bin`, and `flatpak`.
- Build with `makepkg -s --noconfirm`.

## Build

```bash
makepkg -s --noconfirm
```

## Packaging notes

- Keep this package aligned with the browser delivery strategy used by Welcome and the installer.
- Do not use this meta package to silently rename browser package names.

## Troubleshooting

- If installation fails, the problem is usually in one of the dependency packages or in repository availability, not in the empty meta package itself.

## Docs website export notes

- Docs site usage: package-group overview plus the dependency list from this README.
