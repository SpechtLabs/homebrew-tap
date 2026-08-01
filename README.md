# Specht Labs Homebrew Tap

A [Homebrew](https://brew.sh) tap for the command-line tools published by
[Specht Labs](https://github.com/SpechtLabs). It hosts both formulae (under
`Formula/`) and casks (under `Casks/`), so a single tap covers everything we
ship for macOS and Linux.

## Add the tap

```shell
brew tap spechtlabs/tap
```

Once the tap is added, its packages are available to `brew install` like any
other. You can also skip this step and reference the tap inline the first time
you install something (see below).

## Install a package

Replace `<package>` with the name of the tool you want:

```shell
# If you've already run `brew tap spechtlabs/tap`
brew install <package>

# Or install directly without adding the tap first
brew install spechtlabs/tap/<package>
```

The fully-qualified form (`spechtlabs/tap/<package>`) both adds the tap and
installs the package in one step, so a later `brew upgrade` keeps it current.

To see what this tap provides once it's added:

```shell
brew tap-info --json spechtlabs/tap
```

## Upgrade and uninstall

```shell
# Upgrade a single package
brew upgrade <package>

# Upgrade everything, including packages from this tap
brew upgrade

# Remove a package
brew uninstall <package>

# Remove the tap entirely
brew untap spechtlabs/tap
```

## How this tap is maintained

The formulae and casks in this repository are **generated automatically** by
the CD pipelines of each source project when it cuts a release — for example
via [GoReleaser](https://goreleaser.com). Every file under `Formula/` and
`Casks/` carries a `DO NOT EDIT` header for that reason: changes made by hand
are overwritten on the next release.

If a package is out of date or broken, open an issue on the tool's own
repository rather than editing files here.
