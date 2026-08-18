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

# 2026.09.18

## probably annoying, not dangerous

zjv, full Xcode is heavy and fussy, but it is unlikely to permanently screw up your local dev env if you install it normally from the App Store and avoid changing global toolchains manually.

The pain is mostly:

COSTS
* Huge download/install: often 10-20GB+ download, 30-50GB+ installed/derived data/cache over time.
* Time: can easily be 30-90 min depending on network/disk.
* First-run prompts: license, components, simulator runtimes.
* Occasional macOS/Xcode version mismatch.
* Apple signing/provisioning headaches for real-device builds.
* Simulator disk bloat.

RISK TO LOCAL ENV
* Low if you do standard install.
* Medium annoyance if `xcode-select` switches global developer dir and some tools start resolving Apple SDK paths differently.
* Reversible with:
```sh
sudo xcode-select -s /Library/Developer/CommandLineTools
```
or:
```sh
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```

## what changes globally

Installing Xcode itself mostly just adds:

```txt
/Applications/Xcode.app
~/Library/Developer/Xcode
~/Library/Developer/CoreSimulator
```

The global-ish setting is:

```sh
xcode-select -p
```

Right now yours is:

```txt
/Library/Developer/CommandLineTools
```

After Xcode setup, Expo/iOS wants:

```sh
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```

That is the main "env mutation".

## safe install path

LOWEST-RISK ROUTE
```sh
xcode-select -p
```

Install Xcode from App Store.

Then:

```sh
sudo xcodebuild -license accept
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
xcodebuild -version
xcrun simctl list devices available
```

If you want to go back:

```sh
sudo xcode-select -s /Library/Developer/CommandLineTools
```

## cleanup if you hate it

```sh
rm -rf ~/Library/Developer/Xcode/DerivedData
rm -rf ~/Library/Developer/CoreSimulator/Caches
```

Full uninstall is basically:

```sh
sudo rm -rf /Applications/Xcode.app
sudo xcode-select -s /Library/Developer/CommandLineTools
```

I would not casually delete all of `~/Library/Developer` because Command Line Tools and other Apple tooling may use parts of it.

## recommendation

If your goal is daily speed: do not bother.

If your goal is occasional native iOS validation: Xcode is tolerable, and lower-friction than fighting Expo Go/dev-client forever.

Best compromise:
* web-first for daily work
* install Xcode only if you need simulator/native-camera validation
* keep `xcode-select` switchable and documented in `denv/mobile.md`