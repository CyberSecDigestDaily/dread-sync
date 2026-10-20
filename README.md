# dread-sync

Encrypted sync data for the Dread List (https://cybersecdigestdaily.github.io/dread/).

- `vault.json`: the sync token, encrypted with a key derived from a passphrase (PBKDF2-SHA256, 600,000 rounds, AES-256-GCM).
- `state.json`: ratings and settings, encrypted with the same key. Its `taste` field is an optional plaintext summary (film ids only, no dates) used by the nightly rebuild and the weekly curator.

Every save from the page is a commit. Nothing here is readable without the passphrase except `taste`.
