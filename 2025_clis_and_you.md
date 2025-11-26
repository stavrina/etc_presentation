---
theme:
  override:
    slide_title:
      font_size: 3
title: "The command line, package management and you"
sub_title: "An opinionated walkthrough ft. Python"
author: Stavrina Dimosthenous
event: CLARI Group Meeting
date: 2025-11-27
options:
  incremental_lists: true
---

Purpose
===
<!-- font_size: 2 -->
1. Wax poetic
2. Share frustrations
3. Share alternatives
4. Curiosity
5. Confidence

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
  * `pyenv`, `virtualenv`, `pipenv`, `poetry`, `conda`, `mamba`**?!** (⊙_☉)
    * And `poetry` just was not what I needed
  * Docker is great!
    * Not exactly what I need
    * Suitability (subjective)
      * remote work
      * fully isolated environments
    * **BUT!**
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

Reasons why I'm keeping `conda`/`mamba` "( – ⌓ – )
===
<!-- font_size: 2 -->
* "Interoperability"
* `mamba` <- it's great, actually!
* Julia
* I like having my hand held
<!-- end_slide -->

For those reasons... `pixi`!
===
<!-- font_size: 2 -->
* conda-forge
* interoperability
* comparably intuitive commands to `uv`
<!-- end_slide -->


Trying new things is fun...
===
<!-- font_size: 2 -->
* **BUT**
  * **Time**
  * **Reason**

<!-- end_slide -->

Other things to try - Languages
===
<!-- font_size: 2 -->
* Julia
  * `Pkg` in the REPL!
* `cargo`\/`cargo-binstall` (I don't even know what Rust syntax looks like)
<!-- end_slide -->

Other things to try - OS and package managers
===
<!-- font_size: 2 -->
* `pacman` (for Arch)
  * `yay`\/`paru` (I prefer `yay`)
  * Try a new OS (Libre!)
    * Try CachyOS (I use this!), EndeavourOS or Garuda Linux!
    * Lots of Arch resources on [](https://arcolinux.com/)
* `macports` (I also use `brew` but prefer `port`)
* Docker (use on macOS with `colima` and sort out your `.wslconfig` on Windows)
* Chocolatey (on Windows! 🤯)
<!-- end_slide -->

Other things to try - not tested, personally... yet!
===
<!-- font_size: 2 -->
* `eget`
* `asdf`
* `winget`
* `scoop`