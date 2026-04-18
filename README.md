## Tools
Repository for pinned binary tool assets used in local development.

## Purpose

The goal of this repository is to provide a stable and reproducible source of tool binaries for macOS-based development environments.

Included tools:
- `arm-none-eabi` (ARM GNU Toolchain)
- `ninja`
- `clang-format`
- `clang-tidy`

## Distribution model

Tool binaries are stored as **GitHub Release assets**.

This repository should contain:
- release descriptions,
- checksum files.

## Supported platform

Current assets are prepared for:

- `macOS-arm64`
- `Linux-x86`

## Available tool groups

### 1. ARM GNU Toolchain

Used for:
- embedded ARM bare-metal builds,
- local development and CI builds.

Typical release contents:
- ARM GNU Toolchain archive for macOS/Linux
- `SHA256SUMS`

Example asset naming:
- `arm-gnu-toolchain-15.2.rel1-x86_64-arm-none-eabi.tar.xz`
- `SHA256SUMS`

### 2. Ninja

Used for:
- embedded Cmake builds,
- local development and CI builds.

Typical release contents:
- Ninja archive for macOS/Linux
- `SHA256SUMS`

Example asset naming:
- `ninja-linux.tar.xz`
- `SHA256SUMS`

### 3. clang-tidy and clang-format (only for MacOS)

Used for:
- static analysis,
- code quality checks,
- CI validation,
- automatic source formatting,
- consistent code style in local workflows.

Typical release contents:
- `clang-mac.tar.xz` archive for macOS
- `SHA256SUMS`

## Download date

Current mirrored packages were prepared based on downloads collected on:

- `2026-04-18` - arm-none-eabi toolchain v15.2.rel1
- `2026-04-18` - ninja v1.13.2
- `2026-04-10` - clang-tidy and clang-format v22.1.3

## Recommended usage

Consumer repositories should:
1. download required assets from GitHub Releases,
2. verify checksums,
3. unpack tools into a local `tools/` directory,

Example target layout in a consumer repository:

```text
tools/
  arm-none-eabi/
    <version>/
  clang/
    <version>/
  ninja/
```

## Integrity verification

Each release should include a `SHA256SUMS` file.
Example verification on macOS:

```bash
shasum -a 256 <archive-file>
```

## Notes

- This repository is intended for binary distribution and tool version pinning.
- Assets should be treated as external tool dependencies.
- Checksum verification is recommended before every extraction and use.

## Future improvements

This repository may later include:
- installation scripts for macOS,
- support for additional platforms.
