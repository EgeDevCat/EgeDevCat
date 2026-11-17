<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:CE422B,100:2b1a12&height=170&section=header&text=EgeDevCat&fontSize=62&fontColor=ffffff&fontAlignY=36&desc=Rust%20first%20%C2%B7%20C%2B%2B%20when%20it%20matters%20%C2%B7%20Linux%20only&descAlignY=58&descSize=17&animation=fadeIn" alt="EgeDevCat">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=23&duration=2800&pause=900&color=CE422B&center=true&vCenter=true&width=820&height=52&lines=Rust+first.+C%2B%2B+when+it+matters.;Compilers%2C+bytecode+VMs%2C+memory+layout.;Linux+only+%E2%80%94+CachyOS+daily+driver.;Ownership+boundaries+instead+of+lock+files." alt="typed">

<img src="https://skillicons.dev/icons?i=rust,cpp,linux,arch,bash,cmake,csharp,go,java,py,js,ts" alt="Rust, C++, Linux, Arch, Bash, CMake, C#, Go, Java, Python, JS, TS">

<p>
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=CE422B" alt="Rust">
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/CachyOS-1a6bab?style=for-the-badge&logo=archlinux&logoColor=white" alt="CachyOS">
</p>

</div>

## Rust first

Rust is the default. If the problem is state moving between threads, a parser,
an allocator, a compiler pass, a service that must not die at 3am — the first
version starts with `cargo new`, and the borrow checker argues with me long
before the binary ever exists. Ownership, exhaustive `match`, `Result` instead
of exceptions: I would rather fight the type system for an afternoon than chase
a use-after-free for a week.

C++ comes out where the problem is control — explicit allocation, ABI, codegen,
or a build that has to stay inside CMake. That is why
[ketsa](https://github.com/EgeDevCat/ketsa), the language and bytecode VM I
build, is C++ end to end.

```rust
// The shape I keep reusing: an AST nothing else can mutate behind my back.
enum Expr {
    Num(i64),
    Add(Box<Expr>, Box<Expr>),
}

impl Expr {
    fn eval(&self) -> i64 {
        match self {
            Expr::Num(n) => *n,
            Expr::Add(lhs, rhs) => lhs.eval() + rhs.eval(),
        }
    }
}
```

| Rust loop | What I use it for |
| --- | --- |
| `cargo build --release` | Every non-trivial binary; release is the mode I think in. |
| `cargo clippy -- -D warnings` | Warnings are errors, or they are decoration. |
| `cargo fmt` + `rustfmt.toml` | Formatting is not a review topic. |
| `rust-analyzer` | Type-driven editing in a terminal-first setup. |
| `enum` + `Result` + `?` | Error paths as data instead of control flow. |

## What I work on

Compilers and bytecode runtimes, parsers, memory layout — the parts of a program
where an abstraction's cost is the design problem instead of something hidden
behind a framework. Rust is where new systems work starts; C++ is where I want
explicit control over allocation, ABI and generated code.

Everything targets Linux and nothing I ship assumes otherwise. CachyOS is not a
test VM or a second machine — it is the daily driver, so the toolchain is the
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
