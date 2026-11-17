<div align="center">

<h1>EgeDevCat</h1>

<p>
  <b>Low-level developer.</b> Languages, runtimes and the tooling around them &mdash;
  <br>
  built up from source instead of pulled in as dependencies.
</p>

<p>
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <br>
  <img src="https://img.shields.io/badge/CachyOS-1a6bab?style=flat-square&logo=archlinux&logoColor=white" alt="CachyOS">
  <img src="https://img.shields.io/badge/toolchain-CMake%20%C2%B7%20Make%20%C2%B7%20Bash-4E4E4E?style=flat-square" alt="Build tools">
  <img src="https://img.shields.io/badge/editor-terminal--first-1F1F1F?style=flat-square" alt="terminal-first">
</p>

</div>

## What I work on

Most of what I write is close to the machine: compilers, bytecode runtimes,
system-level C++ and single-binary services. When a project needs a piece of
infrastructure that already exists as a heavier dependency, my default is to
write the small version myself and understand it, rather than import it.

That pulled me across a few ecosystems — C++ and CMake for a language
implementation, Go for services that ship as one static binary, Java when the
platform dictates it (Minecraft plugins), C# for Windows-facing tools and
JavaScript/TypeScript for front ends that have to sit on top of the other
pieces.

## Selected projects

| Project | What it is | Stack |
| --- | --- | --- |
| [ketsa](https://github.com/EgeDevCat/ketsa) | A general-purpose language: parser, static type checker, bytecode VM and tooling, with its own wiki and language reference. | C++ · CMake · TypeScript |
| [Blockeum](https://github.com/EgeDevCat/Blockeum) | Visual programming IDE where a real AST is the shared layer, so blocks compile to code and code can be turned back into blocks. | JavaScript · HTML · CSS |
| [OptiByte-DragDrop](https://github.com/EgeDevCat/OptiByte-DragDrop) | Drag-and-drop automation platform (n8n-shaped, MIT) that runs from one Go binary — no Docker, no Node, no separate database. | Go · TypeScript |
| [LagTrace](https://github.com/EgeDevCat/LagTrace) | Minecraft server diagnostics: scans loaded chunks and names the top activity hotspots with coordinates, instead of only printing TPS/MSPT. | Java |
| [Nexus](https://github.com/EgeDevCat/Nexus) | Terminal user authentication and system-information tool over a JSON store. | C# / .NET |
| [NovaExplorer](https://github.com/EgeDevCat/NovaExplorer) | Windows file explorer built on WinUI 3, with packaging for x64, arm64 and x86. | C# · XAML |

## How I build

- **From scratch when the alternative is a dependency.** A compiler, a VM, an
  AST-based editor and a workflow engine each started as their own codebase.
- **Few moving parts at runtime.** Prefer one binary and a config file over a
  stack of containers and sidecars.
- **Types and diagnostics over conventions.** Static checks at compile time,
  actionable output at run time — LagTrace exists because "the server lags" is
  not a debuggable statement.
- **Linux first, always.** Nothing I ship assumes a Windows host, even when
  the target is Windows software.

## Environment

Daily driver: **CachyOS** (Arch-based), used as the only OS, not a side setup.
That means the usual Arch toolchain — `pacman`, `mkarchiso` for live images,
`systemd-boot`, ext4, and a terminal-first workflow. Bash and CMake are part
of the daily loop as much as any language.

<div align="center">

<img height="160" src="https://github-readme-stats.vercel.app/api?username=EgeDevCat&show_icons=true&hide_title=true&hide_border=true&theme=dark" alt="GitHub stats">
<img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=EgeDevCat&layout=compact&hide_border=true&theme=dark" alt="Top languages">

</div>

## Elsewhere

Everything worth looking at is pinned above or listed in the repositories tab.
Open an issue on the project you care about — that is the contact channel I
actually read.
