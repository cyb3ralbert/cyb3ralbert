# cyb3ralbert

Infrastructure engineer. Linux, Kubernetes, Go, Python.

---

## Currently

**Tool-level permissions in MCP servers** — which tools a server actually puts in
`tools/list`, and how to make it hand an agent fewer of them.

The pattern I keep arriving at, which is not original and not complicated: deny writes by
default, grant write tools *by name*, filter the unnamed ones out of the inventory rather
than rejecting them at call time, and fail at startup on an unknown name.

Recent patches:

- [chigwell/telegram-mcp#168](https://github.com/chigwell/telegram-mcp/pull/168) — `read-only+<tool>,<tool>`: a read-only baseline plus named write tools *(merged)*
- [Flux159/mcp-server-kubernetes#356](https://github.com/Flux159/mcp-server-kubernetes/pull/356) — unknown names in `ALLOWED_TOOLS` fail loudly instead of silently *(merged)*
- [redis/mcp-redis#161](https://github.com/redis/mcp-redis/pull/161) — `MCP_REDIS_ALLOWED_TOOLS`, for a server with no tool-level control *(open)*

Notes from reading these servers are in progress.

---

## Write-ups

- [git-crypt + Trezor](https://cyb3ralbert.github.io/git-crypt-trezor/) — repo encryption key never on disk
- [Trezor as a TOTP vault](https://cyb3ralbert.github.io/trezor-totp/) — 2FA secrets encrypted on-device
- [Recovering a Trezor GPG identity from a seed phrase](https://cyb3ralbert.github.io/trezor-gpg-recovery/) — SLIP-0010, no hardware required; answers [trezor-agent#335](https://github.com/romanz/trezor-agent/issues/335)

## Code

- [claude-skills](https://github.com/cyb3ralbert/claude-skills) — reusable Claude Code skills
- [trezor-totp](https://github.com/cyb3ralbert/trezor-totp) · [trezor-gpg-recovery](https://github.com/cyb3ralbert/trezor-gpg-recovery) — implementations behind the write-ups
- [nobsgojobs-go](https://github.com/cyb3ralbert/nobsgojobs-go) — Go client for a free feed of current Go/backend job postings
- [hiddenjump](https://github.com/cyb3ralbert/hiddenjump) — reverse SSH tunnel through CGNAT

---

[site](https://cyb3ralbert.github.io) · [telegram](https://t.me/cyb3ralbert) · [linkedin](https://www.linkedin.com/in/zenops/) · [email](mailto:cyberalbert@protonmail.ch)
