<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:CE422B,100:2b1a12&height=170&section=header&text=EgeDevCat&fontSize=62&fontColor=ffffff&fontAlignY=36&desc=Rust%20and%20C%2B%2B%20systems%20work%20%C2%B7%20Linux%20daily%20driver%20%C2%B7%20Windows%20targets&descAlignY=58&descSize=17&animation=fadeIn" alt="EgeDevCat">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=2800&pause=900&color=CE422B&center=true&vCenter=true&width=820&height=52&lines=Rust+and+C%2B%2B+systems+work.;Compilers%2C+bytecode+VMs%2C+memory+layout.;Linux+daily+driver+on+CachyOS.;Windows+desktop+too+%E2%80%94+C%23+and+WinUI." alt="typed">

<img src="https://skillicons.dev/icons?i=rust,cpp,linux,arch,windows,bash,cmake,csharp,go,java,py,js,ts" alt="Rust, C++, Linux, Arch, Windows, Bash, CMake, C#, Go, Java, Python, JS, TS">

<p>
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=CE422B" alt="Rust">
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/CachyOS-1a6bab?style=for-the-badge&logo=archlinux&logoColor=white" alt="CachyOS">
  <img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows">
</p>

</div>

## What I do

Systems work in Rust and C++: compilers and bytecode runtimes, parsers, memory
layout — code where the cost of an abstraction is part of the design. Rust is
where new work starts; C++ is where I need direct control over allocation, ABI
and codegen, which is why [ketsa](https://github.com/EgeDevCat/ketsa) (a
language and its VM) is C++ end to end.

Linux is the machine I develop on: **CachyOS**, an Arch base with `pacman` +
AUR, GCC/Clang, CMake, `cargo`, `systemd-boot`, ext4 and `mkarchiso` for live
images. That is the environment, not the only target.

I also ship Windows software — C#/.NET desktop tools and WinUI 3 apps packaged
for x64, arm64 and x86 — plus work the platform picks for me: Minecraft plugins
in Java, single-binary services in Go, front ends in JavaScript/TypeScript.

## Stack

| Stack | Used for |
| --- | --- |
| **Rust** | New systems code: parsers, tooling, concurrency. `cargo`, `clippy`, `rustfmt`, `rust-analyzer`. |
| **C++** | Compiler/VM internals and performance-critical paths, built with CMake. |
| **Linux · CachyOS** | Daily driver and dev environment: pacman/AUR, systemd-boot, ext4, mkarchiso. |
| **Windows · .NET** | C# desktop apps, WinUI 3, multi-arch packaging (x64 / arm64 / x86). |
| **Go · Java · TS** | Single-binary services, Minecraft server plugins, front ends. |

## Selected projects

| Project | What it is | Stack |
| --- | --- | --- |
| [ketsa](https://github.com/EgeDevCat/ketsa) | A general-purpose language: parser, static type checker, bytecode VM and tooling, with its own wiki and language reference. | C++ · CMake |
| [Blockeum](https://github.com/EgeDevCat/Blockeum) | Visual programming IDE where a real AST is the shared layer, so blocks compile to code and code can be turned back into blocks. | JavaScript · HTML · CSS |
| [OptiByte-DragDrop](https://github.com/EgeDevCat/OptiByte-DragDrop) | Drag-and-drop automation platform (n8n-shaped, MIT) that runs from one Go binary — no Docker, no Node, no separate database. | Go · TypeScript |
| [LagTrace](https://github.com/EgeDevCat/LagTrace) | Minecraft server diagnostics: scans loaded chunks and names the top activity hotspots with coordinates, instead of only printing TPS/MSPT. | Java |
| [Nexus](https://github.com/EgeDevCat/Nexus) | Terminal user authentication and system-information tool over a JSON store. | C# / .NET |
| [NovaExplorer](https://github.com/EgeDevCat/NovaExplorer) | Windows file explorer built on WinUI 3, packaged for x64, arm64 and x86. | C# · XAML |

## How I build

- **Correctness the compiler can check.** Ownership in Rust, RAII and explicit
  lifetimes in C++ — less to catch in review.
- **Fewer moving parts.** A binary and a config file over containers and
  sidecars.
- **Output that names the problem.** LagTrace exists because "the server lags"
  is not an actionable statement.
- **Portable by default.** Code organised so Linux and Windows targets share
  logic instead of forking it.

## Environment

Development machine: **CachyOS**, an Arch-based, performance-tuned
distribution.

- **Toolchain:** `pacman` + AUR, GCC/Clang, CMake, Make and `cargo` next to
  `mkarchiso`.
- **Boot and storage:** UEFI, `systemd-boot`, ext4.
- **Media:** live images built with `mkarchiso` from a `squashfs` profile with a
  RAM overlay.
- **Workflow:** terminal-first — editor, builds and debugging in the same
  shell.
- **Cross-targets:** Windows builds via .NET / WinUI 3 packaging profiles for
  x64, arm64 and x86.

---

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=EgeDevCat&show_icons=true&hide_title=true&hide_border=true&theme=dark&icon_color=CE422B&include_all_commits=true&rank_icon=github" alt="stats">
<img height="165" src="https://streak-stats.demolab.com?user=EgeDevCat&theme=dark&hide_border=true&border_radius=8&ring=CE422B&fire=CE422B&currStreakLabel=CE422B" alt="streak">

<br>

<img height="185" src="https://github-readme-stats.vercel.app/api/top-langs/?username=EgeDevCat&layout=donut&hide_border=true&theme=dark&langs_count=8" alt="top languages">

<br>

<img width="98%" src="https://github-readme-activity-graph.vercel.app/graph?username=EgeDevCat&bg_color=0d1117&color=CE422B&line=CE422B&point=ffffff&area=true&hide_border=true&custom_title=Contribution%20activity" alt="activity graph">

</div>

---

## Elsewhere

Everything worth looking at is pinned above or listed in the repositories tab.
Open an issue on the project you care about — that is the contact channel I
actually read.
