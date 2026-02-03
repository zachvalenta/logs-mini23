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
