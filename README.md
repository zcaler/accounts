# Accounts Vault

A personal, encrypted backup of my account and wallet information, kept in version
control so I can restore it from anywhere I have an internet connection.

## Purpose

This repository is a secure, portable store for my account data. Every sensitive
value is **encrypted with my personal passphrase** before it is committed — nothing
here is readable without that passphrase. The repo itself only holds ciphertext,
so it can be cloned and synced without exposing the underlying secrets.

## Contents

* **`vault.json`** — The encrypted vault. Contains:

  * `gasFreeApi` — encrypted API `key` and `secret`.
  * `wallets\[]` — a list of wallets, each with:

    * `name` — a human-readable label.
    * `pvk` — the encrypted private key.
    * `passwordHint` — a reminder to help me recall the passphrase for that wallet.
* **`accounts/`** — Date-stamped, password-protected `.rar` archives kept as
point-in-time snapshots of my account data.

## Restoring

To recover a wallet:

1. Clone this repository.
2. Open `vault.json` and locate the wallet by `name` (use the `passwordHint` if you
need a reminder of which passphrase applies).
3. Decrypt the relevant field with your personal passphrase to recover the original
private key, API credentials, etc.

## Security notes

* The passphrase is **never** stored in this repository — without it the contents
cannot be decrypted.
* Keep the passphrase memorized or stored separately and securely. If it is lost,
the encrypted data here is unrecoverable.
* Treat the `passwordHint` fields as reminders only; they should never reveal the
passphrase itself.


### TRC20 gasfree:
```
TAsxZuYAShxahheNSC3LmNKstKK3dN4Nmb
```