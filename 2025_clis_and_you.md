---
theme:
  override:
    slide_title:
      font_size: 3
title: "My favourite package (?) managers"
sub_title: "An account"
author: Stavrina Dimosthenous
event: MRSC
date: 2025-07-24
options:
  incremental_lists: true
---

Purpose
===
<!-- font_size: 2 -->
1. Quality-of-life 
2. Try something new
   * Go forth and explore
3. Secret third thing

<!-- end_slide -->

<!-- jump_to_middle -->


Disclaimers
===

<!-- end_slide -->

Criteria
===
<!-- font_size: 2 -->
* Makes my life easier:
  * ACTUALLY fixes a problem I'm having
  * Command line interface (CLI)
  * One thing!
  * Shareable
  * No bloat **...?** ＼(º □ º l|l)/	

<!-- end_slide -->

`uv`
===
<!-- font_size: 2 -->
* What
  * Python version and environment management (+ a few more things)
* Why
  * Fed up with conda (miniconda)
  * Wanted to go back to `venv`
  * Still needed version management
  * `pyenv`, `virtualenv`, `pipenv`, `poetry`, `conda`, `mamba`...**?!** (⊙_☉)
    * And `poetry` just was not what I needed
  * I suck at docker ╥﹏╥
    * Suitability (subjective)
    * More on this soon...

**I JUST FOUND OUT ABOUT `pixi` 3 days ago**
<!-- end_slide -->

`uv` some commands
===
<!-- new_lines: 6 -->
<!-- column_layout: [3, 4] -->
<!-- column: 0 -->
**Basic usage**

```shell
uv init <dir>
cd <dir>
```

Within `<dir>`
```
├── .gitignore
├── .python-version
├── README.md
├── main.py
└── pyproject.toml
```
<!-- column: 1 -->

Same as

```shell
uv init --app --vcs git <dir>
```

Specify Python version
```shell
uv init --python 3.x <dir>
```

Barebones
```shell
uv init --script <filename>.py
```

<!-- end_slide -->
`uv` some commands
===
<!-- new_lines: 6 -->
<!-- column_layout: [3, 4] -->
<!-- column: 0 -->
**Environment management**
```shell
uv add <packages>
```
```shell
uv remove <packages>
```
```
<dir>
├── .venv
│   ├── bin
│   ├── lib
│   └── pyvenv.cfg
│
```
<!-- column: 1 -->
Similarly
```shell
uv add --requirements requirements.txt
```

<!-- end_slide -->

`uv` some commands
===
<!-- new_lines: 6 -->
<!-- column_layout: [3, 4] -->
<!-- column: 0 -->

**Interoperability**
```shell
uv export -o \
requirements.txt
```

<!-- column: 1 -->
<!-- new_lines: 2 -->
```shell
uv export -o pylock.toml
```
```shell
uv export --no-hashes --no-header \
--no-sources --no-annotate \
-o requirements.txt
```
<!-- reset_layout -->
**Build backend options**

```shell
uv build [--sdist|--wheel] <path>
```

<!-- end_slide -->

Subjective view is subjective
===
<!-- font_size: 2 -->
* `.toml` config!
* shell completion!
* initialises `.git/` for me (with 🔔 and 🪈)
* Integrates well with my text editor (I call it an IDE)
* **NOT** because it's written in Rust (￣ヘ￣)
<!-- end_slide -->

Reasons why I'm keeping `conda` "( – ⌓ – )
===
<!-- font_size: 2 -->
* "Interoperability"
* `mamba`
* Julia
* I like having my hand held
* Need to look into `pixi`
  * It might actually solve all my problems, and tuck me into bed
<!-- end_slide -->

Still...
===
<!-- font_size: 2 -->
* I still want to make okay containerised environments 
* Still locked into *CodeOSS*\/*VSCodium* (˃̣̣̥⌓˂̣̣̥ )
  * Exploring my options
  * And writing theme configs
* Trying new things is fun...
  * **Time**
  * **Reason**

<!-- end_slide -->

Other things to try
===
<!-- font_size: 2 -->
* Julia
  * `Pkg` in the REPL!
* `pacman` (for Arch)
  * `yay`\/`paru` (I prefer `yay`)
    * Obviously, audit and vet everything on AUR!
  * I don't use Arch
    * Try CachyOS (I use this!), EndeavourOS or Garuda Linux!
    * Lots of Arch resources on [](https://arcolinux.com/)
* `cargo`\/`cargo-binstall` (I don't even know what Rust syntax looks like)
* `macports` (I also use `brew` but prefer `port`)
* Docker (use on macOS with `colima` and sort out your `.wslconfig` on Windows)
* `eget` (Full disclosure, not tested this out yet!)
