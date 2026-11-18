<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:CE422B,100:2b1a12&height=180&section=header&text=EgeDevCat&fontSize=64&fontColor=ffffff&fontAlignY=34&desc=C%2B%2B%20%2B%20Rust%20%C2%B7%20compilers%2C%20bytecode%20VMs%2C%20Linux&descAlignY=58&descSize=18&animation=fadeIn" alt="EgeDevCat">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=2600&pause=800&color=CE422B&center=true&vCenter=true&width=760&height=50&lines=C%2B%2B+where+the+metal+shows.;Rust+where+the+compiler+carries+it.;Lexers%2C+type+checkers%2C+bytecode+VMs.;CachyOS+%E2%80%94+terminal+first." alt="typed">

<img src="https://skillicons.dev/icons?i=cpp,rust,linux,arch,bash,cmake,git,vscode,csharp,go,java,py" alt="C++, Rust, Linux, Arch, Bash, CMake, Git, VS Code, C#, Go, Java, Python">

<p>
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=CE422B" alt="Rust">
  <img src="https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white" alt="CMake">
  <img src="https://img.shields.io/badge/CachyOS-1a6bab?style=for-the-badge&logo=archlinux&logoColor=white" alt="CachyOS">
</p>

</div>

## C++ and Rust, end to end

I write compilers and the machines that run what they compile. C++ is the
engine — allocation, ABI, codegen, cache lines. Rust is where new work starts,
because the borrow checker catches what review does not.

| | What it does here |
| --- | --- |
| **C++** | 400 KB+ of it: [ketsa](https://github.com/EgeDevCat/ketsa)'s lexer, static type checker, bytecode VM and JIT scaffold. Hand-written, CMake, no framework between the source and the metal. |
| **Rust** | The default for anything I start now — parsers, CLI tooling, concurrency. `cargo`, `clippy -D warnings`, `rustfmt`, `rust-analyzer`; `unsafe` only where a comment earns it. |

What that looks like as a language I own:

```ketsa
func fibonacci(n: int): int {
    if (n <= 1) return n
    return fibonacci(n - 1) + fibonacci(n - 2)
}

print fibonacci(10)  // 55
```

```bash
./build.sh          # C++20, CMake, GCC or Clang
ketsa run main.ks
```

## Selected work

| Project | What it is | Stack |
| --- | --- | --- |
| **[ketsa](https://github.com/EgeDevCat/ketsa)** | A general-purpose language and its runtime: parser, type checker, bytecode VM, tree-walking interpreter, JIT infrastructure, CLI and [a full language wiki](https://github.com/EgeDevCat/ketsa/tree/main/docs/wiki). | C++ · CMake |
| **[OptiByte-DragDrop](https://github.com/EgeDevCat/OptiByte-DragDrop)** | Automation platform that ships as one Go binary — drag-and-drop wiring, no Docker, no Node, no database to babysit. | Go · TypeScript |
| **[Blockeum](https://github.com/EgeDevCat/Blockeum)** | Visual programming IDE built on a real AST: blocks compile to source, and source decompiles back into blocks. | JavaScript |
| **[LagTrace](https://github.com/EgeDevCat/LagTrace)** | Minecraft server diagnostics that scan loaded chunks and name the hotspots with coordinates — not just another TPS readout. | Java |
| **[NovaExplorer](https://github.com/EgeDevCat/NovaExplorer)** | Windows file manager on WinUI 3, packaged for x64, arm64 and x86. | C# · XAML |

## Rig

**CachyOS** (Arch-based, performance-tuned) is the daily driver: GCC/Clang,
CMake, `cargo`, `pacman` + AUR, `systemd-boot`, ext4, `mkarchiso` for live
images. Windows targets happen too — .NET and WinUI 3, three architectures per
release. Everything else is the platform's choice: Java for Minecraft plugins,
Go for single-binary services.

---

<div align="center">

<img height="160" src="https://github-readme-stats.vercel.app/api?username=EgeDevCat&show_icons=true&hide_title=true&hide_border=true&theme=dark&icon_color=CE422B&include_all_commits=true&rank_icon=github" alt="stats">
<img height="160" src="https://streak-stats.demolab.com?user=EgeDevCat&theme=dark&hide_border=true&border_radius=8&ring=CE422B&fire=CE422B&currStreakLabel=CE422B" alt="streak">

<img height="185" src="https://github-readme-stats.vercel.app/api/top-langs/?username=EgeDevCat&layout=donut&hide_border=true&theme=dark&langs_count=8" alt="language mix">

<img width="98%" src="https://github-readme-activity-graph.vercel.app/graph?username=EgeDevCat&bg_color=0d1117&color=CE422B&line=CE422B&point=ffffff&area=true&hide_border=true&custom_title=Contribution%20activity" alt="activity">

</div>

---

<div align="center">
  <sub>Issues on the repo you care about reach me faster than anything else.</sub>
</div>
