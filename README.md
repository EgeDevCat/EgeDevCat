<div align="center">

<h1>EgeDevCat</h1>

<p>
  <b>Systems programmer &mdash; Rust and C++.</b> Linux is the only platform I target,
  <br>
  and CachyOS is the only system I run on.
</p>

<p>
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust">
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/CachyOS-1a6bab?style=flat-square&logo=archlinux&logoColor=white" alt="CachyOS">
  <img src="https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white" alt="CMake">
  <br>
  <img src="https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
</p>

</div>

## What I work on

Rust and C++ are where the real work happens: compilers and bytecode runtimes,
parsers, memory layout, and the parts of a program where an abstraction's cost
is the design problem rather than something to hide behind a framework. Rust is
my default for new systems code — ownership and exhaustive matching turn whole
classes of bugs into compile errors. C++ is where I want explicit control over
allocation, ABI and generated code; [ketsa](#selected-projects), a language and
its VM, is C++ end to end.

Everything targets Linux, and nothing I ship assumes otherwise. CachyOS is not
a test VM or a second machine — it is the daily driver, so the toolchain is the
Arch one: `pacman` plus the AUR, GCC/Clang, CMake, `cargo`, `systemd-boot`,
ext4, and `mkarchiso` for live images.

The other ecosystems in my repositories — Go for services that ship as one
static binary, Java where a platform dictates it, C# for Windows-facing tools,
JavaScript/TypeScript for the front ends above them — are support work, not the
centre of gravity.

## Focus

| Area | What that means in practice |
| --- | --- |
| **Rust** | New systems code: tooling, safe concurrency, anything where a wrong pointer should be a compile error. |
| **C++** | Performance-critical code and compiler/VM internals — explicit allocation, templates, CMake builds. |
| **Linux** | The only target platform: boot chain, packaging, live media, x86_64 userspace. |
| **CachyOS** | Daily driver on an Arch base — pacman, mkarchiso, systemd-boot, performance kernels. |

## Selected projects

| Project | What it is | Stack |
| --- | --- | --- |
| [ketsa](https://github.com/EgeDevCat/ketsa) | A general-purpose language: parser, static type checker, bytecode VM and tooling, with its own wiki and language reference. | C++ · CMake · Linux |
| [Blockeum](https://github.com/EgeDevCat/Blockeum) | Visual programming IDE where a real AST is the shared layer, so blocks compile to code and code can be turned back into blocks. | JavaScript · HTML · CSS |
| [OptiByte-DragDrop](https://github.com/EgeDevCat/OptiByte-DragDrop) | Drag-and-drop automation platform (n8n-shaped, MIT) that runs from one Go binary — no Docker, no Node, no separate database. | Go · TypeScript |
| [LagTrace](https://github.com/EgeDevCat/LagTrace) | Minecraft server diagnostics: scans loaded chunks and names the top activity hotspots with coordinates, instead of only printing TPS/MSPT. | Java |
| [Nexus](https://github.com/EgeDevCat/Nexus) | Terminal user authentication and system-information tool over a JSON store. | C# / .NET |
| [NovaExplorer](https://github.com/EgeDevCat/NovaExplorer) | Windows file explorer built on WinUI 3, with packaging for x64, arm64 and x86. | C# · XAML |

## How I build

- **Memory is the design.** Ownership boundaries in Rust, RAII and explicit
  lifetimes in C++ — correctness a compiler can check, not a comment asking
  politely.
- **No runtime I did not write.** A compiler, a VM, an AST-based editor and a
  workflow engine each started as their own codebase instead of an import.
- **One artefact where possible.** A single binary plus a config file beats a
  stack of containers and sidecars.
- **Diagnostics over conventions.** Static checks at compile time, actionable
  output at run time — LagTrace exists because "the server lags" is not a
  debuggable statement.
- **Linux first, always.** Nothing I ship assumes a Windows or macOS host, even
  when the target is Windows software.

## Environment

Daily driver: **CachyOS**, an Arch-based, performance-tuned distribution, used
as the only OS rather than a side setup. Practical consequences:

- **Toolchain:** `pacman` + AUR, GCC/Clang, CMake, Make and `cargo` on the same
  machine as `mkarchiso`.
- **Boot and storage:** UEFI only, `systemd-boot`, ext4.
- **Media:** live images built with `mkarchiso` from a `squashfs` profile with a
  RAM overlay.
- **Workflow:** terminal-first — editors, builds and debugging in the same
  shell.

<div align="center">

<img height="160" src="https://github-readme-stats.vercel.app/api?username=EgeDevCat&show_icons=true&hide_title=true&hide_border=true&theme=dark" alt="GitHub stats">
<img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=EgeDevCat&layout=compact&hide_border=true&theme=dark" alt="Top languages">

</div>

## Elsewhere

Everything worth looking at is pinned above or listed in the repositories tab.
Open an issue on the project you care about — that is the contact channel I
actually read.
