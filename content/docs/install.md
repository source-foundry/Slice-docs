---
title: "Install"
weight: 3
---

Install the application on your platform with the following instructions.

## macOS

### Homebrew installation

macOS users can install, upgrade, and uninstall Slice with [Homebrew](https://brew.sh/) and the Source Foundry tap room.

Use the following commands to install:

```sh
brew tap source-foundry/taproom
brew update
brew install --cask sourcefoundry-slice
```

Upgrade to new Slice versions with:

```sh
brew upgrade sourcefoundry-slice
```

Homebrew will update Slice to new releases during the `brew update && brew upgrade` process. Use `brew upgrade sourcefoundry-slice` to upgrade the Slice application only.

Use the following command to uninstall:

```sh
brew uninstall sourcefoundry-slice
```

### macOS dmg Installer

Download the [latest macOS dmg installer](https://github.com/source-foundry/Slice/releases/latest) in our Releases.

Launch the installer and acknowledge the license during the install process. Drag and drop the Slice.app bundle into your Applications directory when the installer prompts you to do so. Open Launchpad and launch Slice by clicking the icon.

Repeat the process with a new repository release installer to upgrade to a new Slice release.

Drag the Slice.app bundle from the Applications directory to the Trash to uninstall.

## Windows

Download the [latest Windows .exe installer](https://github.com/source-foundry/Slice/releases/latest) in our Releases.

Launch the installer, acknowledge the license, and follow the instructions. You will have the option to set a desktop icon during installation.  When the install process completes, type "Slice" in the Win 10 Search bar or click the desktop icon to launch the application.

## Linux

### Run from source

This is the recommended approach on Linux distributions because it uses our tested build dependency versions.

Clone the repository with:

```sh
git clone https://github.com/source-foundry/Slice.git
```

Create a Python 3.6+ virtual environment with:

```sh
cd Slice
python3 -m venv .venv
```

Install the required build dependencies with:

```sh
source .venv/bin/activate
pip install -r requirements.txt
```

Run the application with:

```sh
make run
```

### Install from PyPI

This approach does not take advantage of the tested dependency versions but is available for users who want ~~to live on the wild side~~ easy access.

Install with Py3.6+ `pip` using:

```sh
pip install slicegui
```

Run with:

```sh
slicegui
```

### Linux packages

Arch Linux users can install the [slice AUR package](https://aur.archlinux.org/packages/slice/).
