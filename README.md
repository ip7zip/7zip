# 7-Zip

7-Zip is a free, open-source file archiver with a high compression ratio. It was created by Igor Pavlov.

This repository contains the 7-Zip source code. The project website, with downloads, documentation and support information, is **<https://www.7-zip.org>**.

## Contents

- [Features](#features)
- [Download](#download)
- [Building from source](#building-from-source)
  - [Windows (MSVC)](#windows-msvc)
  - [Linux and macOS](#linux-and-macos)
- [Repository layout](#repository-layout)
- [Documentation](#documentation)
- [Reporting issues and getting help](#reporting-issues-and-getting-help)
- [License](#license)

## Features

- High compression ratio in the 7z format, using the LZMA and LZMA2 methods.
- Packing and unpacking of 7z, XZ, BZIP2, GZIP, TAR, ZIP and WIM archives.
- Unpacking of many other archive and disk-image formats. The full, current list is on the [7-Zip website](https://www.7-zip.org).
- AES-256 encryption for 7z and ZIP archives.
- Windows: file manager, shell integration and self-extracting archives.
- Command-line versions for Windows, Linux and macOS.

## Download

Official installers and packages are available from the download page on the project website:

<https://www.7-zip.org/download.html>

Tagged releases and their release notes are listed on the [Releases](../../releases) page of this repository.

## Building from source

The sections below are a quick start. For supported compilers, build options and platform notes, see [`DOC/readme.txt`](DOC/readme.txt).

### Windows (MSVC)

1. Open a Visual Studio command prompt for your target architecture (for example, *x64 Native Tools Command Prompt*), or run the matching `vcvars*.bat` script from your Visual Studio installation.
2. Build the main project:

   ```bat
   cd CPP\7zip
   nmake
   ```

To build only the standalone console version (`7za.exe`):

```bat
cd CPP\7zip\Bundles\Alone
nmake
```

### Linux and macOS

Build the standalone console version (`7zz`) with `make`:

```sh
cd CPP/7zip/Bundles/Alone2
make -j -f ../../cmpl_gcc.mak
```

Other makefiles in `CPP/7zip` cover specific compilers and targets, for example `cmpl_gcc_x64.mak` (x86-64 with assembler) and `cmpl_mac_arm64.mak` (macOS on Apple silicon). Pick the one that matches your platform and use it in place of `cmpl_gcc.mak` in the command above.

## Repository layout

| Directory | Contents |
| --------- | -------- |
| `Asm`     | Assembler sources for optimized code paths |
| `C`       | Source code written in C |
| `CPP`     | Source code written in C++, including the 7-Zip applications under `CPP/7zip` |
| `DOC`     | Documentation and license files |

## Documentation

- [`DOC/readme.txt`](DOC/readme.txt): source package notes and build instructions
- [`DOC/License.txt`](DOC/License.txt): license terms
- User documentation and the command-line reference: <https://www.7-zip.org/faq.html>

## Reporting issues and getting help

For bug reports, questions and other support information, see the support page on the project website:

<https://www.7-zip.org/support.html>

## License

7-Zip is free software distributed under the GNU LGPL. Files in `CPP/7zip/Compress/Rar*` are covered by the GNU LGPL with an additional unRAR restriction. See [`DOC/License.txt`](DOC/License.txt) for the exact terms and for which files are covered by which license.
