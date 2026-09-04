# cyb3ralbert

Infrastructure engineer. Linux, Kubernetes, Go, Python.

Most of what's here shares one property: **self-custody**. Whatever unlocks a thing stays
with the person the thing belongs to — not in a vendor's database, not in a CI secret, not
in a config file sitting next to the data it protects.

---

## Currently

**Bitcoin Core** — small patches, and commits signed by a hardware device rather than by a
key on disk. [Pull requests](https://github.com/bitcoin/bitcoin/pulls?q=author%3Acyb3ralbert).

**Kubernetes The Hard Way**, starting one step before the tutorial does. It opens by asking
for four Debian 12 machines and never says where they come from —
[chapter-zero](https://github.com/cyb3ralbert/chapter-zero) is that step: libvirt/KVM
cloud-image VMs and cloud-init profiles on a host you already have, instead of four rented
instances.

---

## Self-custody, concretely

- [trezor-totp](https://github.com/cyb3ralbert/trezor-totp) — TOTP secrets encrypted at
  rest. The AES key is derived on the Trezor from a fixed BIP32 node and never leaves it;
  only ciphertext is on disk.
- [trezor-gpg-recovery](https://github.com/cyb3ralbert/trezor-gpg-recovery) — rebuild a
  Trezor-backed GPG identity from the seed phrase alone, in software, so you can confirm
  the fingerprint reproduces while you still have the device (SLIP-0010). Related:
  [romanz/trezor-agent#335](https://github.com/romanz/trezor-agent/issues/335).
- [git-crypt + Trezor](https://cyb3ralbert.github.io/git-crypt-trezor/) — the repository's
  encryption key is unwrapped by the device on demand and never written to disk.
- [hiddenjump](https://github.com/cyb3ralbert/hiddenjump) — reach a machine behind CGNAT
  over an SSH tunnel you run yourself, rather than a third-party remote-access service.

The same question turns up away from hardware: which tools an MCP server hands an agent in
`tools/list`, and how to make it hand over fewer.

- [chigwell/telegram-mcp#168](https://github.com/chigwell/telegram-mcp/pull/168) —
  `read-only+<tool>,<tool>`: a read-only baseline plus write tools granted by name *(merged)*
- [Flux159/mcp-server-kubernetes#356](https://github.com/Flux159/mcp-server-kubernetes/pull/356) —
  unknown names in `ALLOWED_TOOLS` fail at startup instead of silently *(merged)*
- [redis/mcp-redis#161](https://github.com/redis/mcp-redis/pull/161) —
  `MCP_REDIS_ALLOWED_TOOLS`, for a server with no tool-level control *(open)*

---

## Write-ups

- [What MCP servers actually expose](https://cyb3ralbert.github.io/mcp-tool-exposure/) —
  six codebases read line by line, with a file and line for every claim. Corrections
  welcome; the documentation-based survey that preceded it was wrong in both directions.
- [Recovering a Trezor GPG identity from a seed phrase](https://cyb3ralbert.github.io/trezor-gpg-recovery/)
- [Trezor as a TOTP vault](https://cyb3ralbert.github.io/trezor-totp/)
- [git-crypt + Trezor](https://cyb3ralbert.github.io/git-crypt-trezor/)

---

## Support

All of the above is unpaid. Bitcoin on-chain, if it was worth something to you:

```
bc1qsjxlel37xp7yjmgwkhkk3k4kntmff6gyznwxhp
```

Mainnet, native SegWit (P2WPKH). Nothing is gated behind it and nothing will be — an issue
or a correction still counts for more. Details: [kramgasse.com/donate](https://kramgasse.com/donate/).

---

[site](https://cyb3ralbert.github.io) · [telegram](https://t.me/cyb3ralbert) · [email](mailto:cyberalbert@protonmail.ch)
