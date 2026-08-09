# Command Line Tools for Xcode

## Purpose
Tracks macOS Command Line Tools installations and updates.

## Current Installation
- Version: 26.2.0.0.1.1764812424
- Date checked: 2026-02-02
- Path: /Library/Developer/CommandLineTools
- xcode-select version: 2416

## Installation History

### 2026-02-02 - Version 26.2.0 (current)
**Reason**: Updated for incplot Formula compilation (requires Xcode 26+)
**Method**: `sudo rm -rf /Library/Developer/CommandLineTools && sudo xcode-select --install`
**Verification**:
```bash
xcode-select --version        # xcode-select version 2416
xcode-select -p              # /Library/Developer/CommandLineTools
pkgutil --pkg-info=com.apple.pkg.CLTools_Executables | grep version
# version: 26.2.0.0.1.1764812424
```

### 2026-02-02 - Version 14.3.1 (pre-update)
**Reason**: Baseline before updating
**Method**: Unknown (pre-existing installation)
**Verification**:
```bash
# version: 14.3.1.0.1.1683849156
```

---

## Notes
- Command Line Tools required for: Homebrew, compiling from source
- Update via: System Settings > Software Update, or `sudo rm -rf /Library/Developer/CommandLineTools && sudo xcode-select --install`
- Check if update needed: `softwareupdate --list`

# COLLIGO

> How painful to get going w/ npm run ios? Assuming I need to install Xcode but worried that my screw up my existing install of the xcode command line tools, see @/Users/zach/Documents/denv/logs/

Moderate pain. Biggest issue is not breaking CLT, it is disk/time and Xcode first-run setup.

`npm run ios` is:

```sh
expo run:ios
```

Given no existing `ios/` dir, Expo will likely generate native iOS project files, then build via Xcode tooling.

## risk to existing command line tools

Low, if you install Xcode normally from App Store / Apple Developer.

Your CLT log says current CLT is:

```txt
/Library/Developer/CommandLineTools
Version: 26.2.0
```

Installing full Xcode should not delete that directory. The thing that changes behavior is `xcode-select`.

After installing Xcode, macOS may point developer tools at:

```sh
/Applications/Xcode.app/Contents/Developer
```

instead of:

```sh
/Library/Developer/CommandLineTools
```

That can affect builds, but it is reversible:

```sh
sudo xcode-select -s /Library/Developer/CommandLineTools
```

For iOS builds, you usually want Xcode selected:

```sh
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```

So the blast radius is mostly a switchable path, not permanent damage.

## Expected steps

1. Install Xcode.
2. Open Xcode once and accept license/install components.
3. Select Xcode tools:

```sh
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
sudo xcodebuild -license accept
```

4. From mobile:

```sh
npm run ios
```

## Pain points

* Xcode download is huge.
* First build can take a while.
* Expo may create `ios/` native project files.
* Simulator runtime may need additional download.
* Signing can get annoying if building to real device; simulator is easier.

## Least-blast-radius option

Before running:

```sh
xcode-select -p
```

After done with iOS work, restore CLT if desired:

```sh
sudo xcode-select -s /Library/Developer/CommandLineTools
```

I would treat `npm run ios` as feasible but heavier than Expo Go / Android. If you just need UI iteration, skip it for now.
