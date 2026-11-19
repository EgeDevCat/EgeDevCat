<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:05080d,55:0a3f7d,100:0a63c0&height=200&section=header&text=EgeDevCat&fontSize=62&fontColor=ffffff&fontAlignY=31&desc=an%20AI%20may%20operate%20this%20machine%20%E2%80%94%20it%20may%20never%20own%20it&descAlignY=50&descSize=17&animation=fadeIn" alt="EgeDevCat">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=21&duration=2800&pause=900&color=00A8FF&center=true&vCenter=true&width=820&height=50&lines=The+OS+decides.+The+model+only+asks.;Tier+2+has+no+approval+path%2C+by+design.;Python+3.12%2C+stdlib+only%2C+fail+closed.;bubblewrap+%2B+seccomp+%2B+cgroup+v2.;CachyOS%2C+terminal+first." alt="typed">

<img src="https://skillicons.dev/icons?i=c,cpp,py,linux,arch,cmake,bash,git,cs,java,vscode&theme=dark" alt="C, C++, Python, Linux, Arch, CMake, Bash, Git, C#, Java, VS Code">

<p>
<img src="https://img.shields.io/badge/Python%203.12-stdlib%20only-0B63CE?style=flat-square&logo=python&logoColor=white" alt="Python 3.12, stdlib only">
<img src="https://img.shields.io/badge/sandbox-bwrap%20%2B%20seccomp%20%2B%20cgroup-0d1117?style=flat-square&logo=linux&logoColor=00A8FF" alt="bubblewrap, seccomp, cgroup v2">
<img src="https://img.shields.io/badge/oracle-Ed25519%20signed-00A8FF?style=flat-square" alt="Ed25519 signed oracle">
<img src="https://img.shields.io/badge/API-JSON--RPC%20v1.2-1F6FEB?style=flat-square&logo=json&logoColor=white" alt="JSON-RPC v1.2">
</p>

</div>

<br>

## Parametral OS

<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/EgeDevCat/parametral-os/master/assets/parametral-mark-256.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/EgeDevCat/parametral-os/master/assets/parametral-mark-light.svg">
  <img src="https://raw.githubusercontent.com/EgeDevCat/parametral-os/master/assets/parametral-mark-light.svg" width="170" alt="Parametral OS">
</picture>

**An Arch + Nix system an AI can operate — but never own.**

<img src="https://img.shields.io/badge/tests-197%20passing-brightgreen?style=flat-square" alt="tests">
<img src="https://img.shields.io/badge/isolation-proof%20generated-00A8FF?style=flat-square" alt="isolation proof">
<img src="https://img.shields.io/badge/platform-Arch%20%2B%20Nix-1793d1?style=flat-square" alt="platform">
</div>

The AI is treated as untrusted code with good intentions. It gets one socket, a short-lived capability token per operation, a sandbox per job, and a human gate for anything that touches the real machine. A separate deterministic oracle refuses a fixed list of irreversible operations *before* policy, tokens or approvals are consulted — it answers from a place the model cannot reach.

```mermaid
flowchart LR
    M["AI model<br/>untrusted"] -->|"socket"| G["parametrald<br/>JSON-RPC v1.2"]
    G --> O{"hard-deny<br/>oracle"}
    O -->|"refused"| X["tier 2<br/>stopped"]
    O -->|"pass"| P{"policy<br/>default deny"}
    P -->|"no rule"| Y["deny"]
    P -->|"allow"| T["token<br/>TTL + scope"]
    P -->|"real write"| A["approval<br/>+ snapshot"]
    T --> S["sandbox<br/>bwrap + seccomp"]
    A --> S
    S --> L["audit<br/>hash chain"]
    X --> L
    Y --> L

    classDef hot fill:#0B63CE,stroke:#00A8FF,color:#ffffff
    classDef cold fill:#0d1117,stroke:#30363d,color:#c9d1d9
    classDef die fill:#2d1117,stroke:#f85149,color:#ffb3b3
    class G,O,P hot
    class M,T,S,A,L cold
    class X,Y die
```

| Tier | What it permits | Cost of being wrong |
| :---: | --- | --- |
| **0** | rootless Nix profile inside a sandbox | nothing — throw the sandbox away |
| **1** | a real system write | an approval, a snapshot, a reviewed preset; no generic exec path |
| **2** | the irreversible | no path exists — not even a valid token buys one |

**[→ github.com/EgeDevCat/parametral-os](https://github.com/EgeDevCat/parametral-os)** &nbsp;·&nbsp; [API v1](https://github.com/EgeDevCat/parametral-os/blob/master/docs/API-v1.md) &nbsp;·&nbsp; [architecture](https://github.com/EgeDevCat/parametral-os/blob/master/docs/ARCHITECTURE.md) &nbsp;·&nbsp; [roadmap](https://github.com/EgeDevCat/parametral-os/blob/master/docs/ROADMAP.md)

## On the bench

| Project | What it is | Stack |
| --- | --- | --- |
| [ketsa](https://github.com/EgeDevCat/ketsa) | a general-purpose language: hand-written lexer, static type checker, bytecode VM, tree-walking interpreter, its own wiki | C++20 · CMake |
| [LagTrace](https://github.com/EgeDevCat/LagTrace) | Minecraft server diagnostics that name the hot chunks with coordinates instead of printing another TPS number | Java |
| [NovaExplorer](https://github.com/EgeDevCat/NovaExplorer) | Windows file manager on WinUI 3, packaged for x64 / arm64 / x86 | C# · XAML |
| [Nexus](https://github.com/EgeDevCat/Nexus) | terminal identity and system-inspection tool, JSON-backed | C# |

## How I work

- **Trust boundaries, not vibes.** If a decision can't be made by a process the model cannot write to, it isn't a security decision — it's a hope.
- **Stdlib first.** The gateway imports nothing third-party. Fewer moving parts isn't minimalism, it's something you can actually prove.
- **Fail closed.** Oracle gone means refuse, not warn. A swallowed exception is a vulnerability with good manners.
- **Tests that try to break it.** Sandbox escape, token scope, audit tampering, foreign uid on a socket — each one has a case that attempts it.
- **Contract before code.** The wire format is written and frozen first; the implementation catches up.

## The machine

CachyOS (Arch-based) is the daily driver — GCC, Clang, CMake, `cargo`, `pacman` + AUR, `systemd-boot`, `mkarchiso` when a live image is needed, fish as the shell. Windows targets happen too, mostly .NET and WinUI 3. No Docker anywhere in the loop: one binary beats a stack of manifests.

<div align="center">

<br>

<img height="165" src="https://github-readme-stats.vercel.app/api?username=EgeDevCat&show_icons=true&hide_title=true&hide_border=true&theme=dark&bg_color=0d1117&icon_color=00A8FF&rank_icon=github" alt="stats">
<img height="165" src="https://streak-stats.demolab.com?user=EgeDevCat&theme=dark&hide_border=true&border_radius=8&background=0d1117&ring=00A8FF&fire=00A8FF&currStreakLabel=00A8FF" alt="streak">

<img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=EgeDevCat&layout=donut&hide_border=true&theme=dark&bg_color=0d1117&title_color=00A8FF&langs_count=7" alt="languages">

<img width="98%" src="https://github-readme-activity-graph.vercel.app/graph?username=EgeDevCat&bg_color=0d1117&color=00A8FF&line=0B63CE&point=ffffff&area=true&hide_border=true&custom_title=Contribution%20activity" alt="activity">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:00A8FF,60:0B63CE,100:061019&height=110&section=footer" alt="">

<sub>Issues on the repo you care about reach me faster than anything else.</sub>

</div>
