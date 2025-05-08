+++
title = "Supported command line environments"
date = 2024-05-14T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>3.1 </b>"
+++

The autocomplete feature of Amazon Q for command line is supported on macOS and specific Linux environments, including AppImage and Ubuntu.

The following environments are supported for both macOS and Linux:

- Shells: bash, zsh, fish

- CLIs: Over 500 of the most popular CLIs such as git, aws, docker, npm, and yarn

### macOS

Amazon Q for command line integrates with the following environments for macOS:

- Terminal emulators: iTerm2, macOS terminal, Hyper, Alacritty, Kitty, WezTerm. To see the full list of terminals, see the Amazon Q for command line [open source code](https://github.com/aws/amazon-q-developer-cli/blob/main/crates/fig_util/src/terminal.rs).

- IDEs: VS Code terminal, Jetbrains terminals (except Fleet)

- macOS 10.15 (Catalina) or later

- Architecture: x86_64 (Intel) or arm64 (Apple Silicon)

### Linux

Amazon Q for command line integrates with the following environments for Linux:

- Platform requirements: Amazon Q for command line for Linux supports Ubuntu 22 and 24, and compatibility for a subset of features on Ubuntu 20. It may otherwise work with GNOME v42+ or environments where the display server is Xorg and the input method framework is IBus.

- Terminal emulators: GnomeConsole, GnomeTerminal, Kitty, Hyper, WezTerm, Alacritty, Tilix, Terminator

- Architecture: x86_64 or aarch64

- Note: Desktop functionality is currently only available on x86_64 architecture

### Windows

Amazon Q for command line works in Linux environments running the Windows Subsystem for Linux (WSL). This environment supports autocomplete, which requires a full installation and terminal specific support. It also supports inline completion for zsh, which works with a minimal installation and is terminal agnostic. A full installation provides a GUI dashboard while minimal installation doesn't.

### Natural languages

Amazon Q Developer provides multi-natural-language support for the Amazon Q Developer command-line interface (CLI). Some of the supported natural languages include Mandarin, French, German, Italian, Japanese, Spanish, Korean, Hindi, and Portuguese, with more languages available.

To utilize this functionality, you can initiate a conversation with Amazon Q Developer using your preferred natural language. Amazon Q automatically detects the language and provides responses in the appropriate language.
