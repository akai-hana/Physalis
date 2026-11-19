<div align="center">

# Physalis
###### Authenticated, locally encrypted data vault.

<!-- image goes here -->

</div>

> [!WARNING]
> This project has just started. \
> Come back later for an actual repository.

# About

Physalis is an authenticated, locally encrypted data vault, written in Rust.

It features a user-authenticated storage vault to locally store any data inside: from plain text to entire videos, and any other media.

This vault is equipped with several cybersecurity/cryptography techniques, making it truly viable for real-world usage.

# Security Architecture

* **Argon2id:** Derives the master encryption key using memory-hard hashing and unique salts to resist brute-force attacks.
* **Two-Tier Key Hierarchy:** Separates the password-derived key from a random 256-bit file key, allowing password updates without vault re-encryption.
* **XChaCha20-Poly1305:** Encrypts files and detects tampering using authenticated tags.
* **Chunked Streaming:** Processes large media in isolated blocks to keep RAM usage low and prevent block-reordering attacks.
* **Encrypted Metadata Index:** Hides original filenames, folder structures, and attributes inside an encrypted database.
* **Rate Limiting & MFA:** Throttles failed login attempts with exponential backoff, with optional 2FA support.
* **Memory Zeroization & Auto-Lock:** Wipes sensitive keys from RAM upon closing or inactivity and locks memory pages against disk swapping.

---

<div align="center">

</> with <3 by [akai_hana](https://github.com/akai-hana)

</div>
