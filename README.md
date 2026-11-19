<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/EgeDevCat/parametral-os/master/assets/parametral-mark-256.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/EgeDevCat/parametral-os/master/assets/parametral-mark-light.svg">
  <img src="https://raw.githubusercontent.com/EgeDevCat/parametral-os/master/assets/parametral-mark-light.svg" width="150" alt="Parametral OS">
</picture>

<h1>EgeDevCat</h1>

<p><b>I build the layer between an AI and a real machine.</b><br>
Operating systems, languages, and the boring machinery that has to say no.</p>

<p>
<code>CachyOS</code> · <code>Python 3.12 · stdlib only</code> · <code>C++20</code> · <code>bubblewrap + seccomp</code> · <code>Ed25519</code> · <code>JSON-RPC</code>
</p>

</div>

## What I'm actually doing

Almost all of it goes into **[Parametral OS](https://github.com/EgeDevCat/parametral-os)** — an Arch + Nix system an AI is allowed to operate but never own. The interesting part was never the model. It is the component that decides whether the model gets to run `rm -rf` on your disk, and answers *no* from a place the model cannot reach.

Everything else I build orbits that same question in a different dialect: a language where the compiler has to be right, a plugin that names the chunk that is burning your server, a file manager that does not lie about what is on disk.

## Parametral OS

Test-first, stdlib-first, and honest about which half exists. The OS side is here; the model side lives elsewhere and reaches it only through one socket.

```
hard-deny oracle  →  policy (default deny)  →  capability token  →  handler  →  audit
deterministic         allow / approval         Ed25519 + TTL        sandbox     hash chain
signed, read-only     no rule → deny           scope + use cap      cgroup      tamper-evident
```

| Tier | What it permits | Cost of being wrong |
| --- | --- | --- |
| **0** | rootless Nix profile inside a sandbox | nothing: throw the sandbox away |
| **1** | a real system write | an approval, a snapshot, a reviewed preset — no generic exec |
| **2** | the irreversible | no path exists. Not even a valid token can buy one |

| Half | Contents | Where it stands |
| --- | --- | --- |
| **OS** | gateway, policy engine, tokens, approvals, hash-chained audit, bwrap sandbox, `sysapply`, install kit | runs, tested, isolation proof generated |
| **AI** | model family, agent loop, experts | separate project, one JSON-RPC contract between them |

**[→ the repo](https://github.com/EgeDevCat/parametral-os)** · [API v1 contract](https://github.com/EgeDevCat/parametral-os/blob/master/docs/API-v1.md) · [architecture](https://github.com/EgeDevCat/parametral-os/blob/master/docs/ARCHITECTURE.md) · [roadmap](https://github.com/EgeDevCat/parametral-os/blob/master/docs/ROADMAP.md)

## The rest of the bench

| Project | What it is | Stack |
| --- | --- | --- |
| [ketsa](https://github.com/EgeDevCat/ketsa) | a general-purpose language: hand-written lexer, static type checker, bytecode VM, tree-walking interpreter, its own wiki | C++20 · CMake |
| [LagTrace](https://github.com/EgeDevCat/LagTrace) | Minecraft server diagnostics that name the hot chunks with coordinates instead of printing another TPS number | Java |
| [NovaExplorer](https://github.com/EgeDevCat/NovaExplorer) | Windows file manager on WinUI 3, packaged for x64 / arm64 / x86 | C# · XAML |
| [Nexus](https://github.com/EgeDevCat/Nexus) | terminal identity and system-inspection tool, JSON-backed | C# |

## How I work

- **Trust boundaries, not vibes.** If a decision can't be made by a process the model cannot write to, it isn't a security decision — it's a hope.
- **Stdlib first.** The gateway imports nothing third-party. Fewer moving parts is not minimalism, it's something you can actually prove.
- **Fail closed.** Oracle gone means refuse, not warn. A swallowed exception is a vulnerability with good manners.
- **Tests that try to break it.** Sandbox escape, token scope, audit tampering, foreign uid on a socket — each one has a case that attempts it.
- **Contract before code.** The wire format gets written and frozen first; the implementation catches up.

## The machine

CachyOS (Arch-based) is the daily driver — GCC, Clang, CMake, `cargo`, `pacman` + AUR, `systemd-boot`, `mkarchiso` when a live image is needed, fish as the shell. Windows targets happen too, mostly .NET and WinUI 3. No Docker anywhere in the loop: I would rather ship one binary than a stack of manifests.

---

<div align="center">

<sub>Issues on the repo you care about reach me faster than anything else.</sub>

</div>
