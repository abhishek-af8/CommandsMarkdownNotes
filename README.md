# CommandsMarkdownNotes

A **personal Linux, WSL, Git, and GCC commands cheat sheet** for quick reference and learning.  
This repository contains my curated `commands.md` file, organized to help with navigation, file management, Git workflows, and compilation processes.

---

## Table of Contents

- [Symbols (VS Code Snippet Prefixes)](#symbols-vs-code-snippet-prefixes)
- [Compilation & Execution](#compilation--execution)
- [Navigation](#navigation)
- [File Management](#file-management)
- [Directory Management](#directory-management)
- [Navigation Shortcuts](#navigation-shortcuts)
- [Backup & Transfer (WSL ↔ Windows)](#backup--transfer-wsl-↔-windows)
  - [WSL → Windows](#wsl-→-windows)
  - [Windows → WSL](#windows-→-wsl)
- [Git: Backing Up Specific Folders](#git-backing-up-specific-folders)
  - [Case 1: Only one directory](#case-1-only-systemcalls)
  - [Case 2: A group of directories](#case-2-systemcalls--linking)
  - [Case 3: Exclude everything except some directories](#case-3-exclude-everything-except-systemcalls-and-linking)
- [Git Update/Push Workflow](#git-updatepush-workflow)
- [Git Enhancements](#git-enhancements)
- [Git Pull & Merge Notes (Collaboration & Safety)](#git-pull--merge-notes-collaboration--safety)
  - [Why Pull Before Push](#why-pull-before-push)
  - [What git pull origin main Does](#what-git-pull-origin-main-does)
  - [Why Conflicts Happen](#why-conflicts-happen)
  - [Types of Merges](#types-of-merges)
  - [Step-by-Step Collaborative Workflow](#step-by-step-collaborative-workflow)
- [GCC Compilation Phases & Commands](#gcc-compilation-phases--commands)
  - [Preprocessing](#preprocessing-c--preprocessed-c)
  - [Compilation](#compilation-cpreprocessed-c--assembly)
  - [Assembly](#assembly-assembly--object-code)
  - [Linking](#linking-object-files--executable)
- [Tips](#tips)

---

## About

This cheat sheet is designed for **practical learning and reference** while working on Linux, WSL, and programming projects.  
It includes:

- Linux navigation and file/directory management commands
- WSL shortcuts and backup/transfer commands
- Git workflows, including pull, push, merge, and update strategies
- GCC compilation phases with examples
- VS Code snippet symbols for quick reference
  > Note: These are personal snippet keywords set up in my VS Code environment. They will only expand into symbols on my system.  
  > 
  > If you want the same functionality:
  > 1. Open VS Code → `File` → `Preferences` → `User Snippets`.
  > 2. Choose `New Global Snippets file` (e.g., `symbols.code-snippets`).
  > 3. Add your snippet JSON entries, for example:
  > 
  > ```json
  > {
  >   "Right Arrow": {
  >     "prefix": "rarrow",
  >     "body": ["→"],
  >     "description": "Insert a right arrow"
  >   }
  > }
  > ```
  > 4. Save the file. Now typing `rarrow` + `Tab` will insert `→`.

> This file evolves as I learn and refine my skills. Future versions will include examples, syntax highlighting, and categorized sections.

## Contents

- `commands.md` → The main cheat sheet file with all commands and workflows.

---
## Usage

### 1. Clone the repository to your local machine:

```bash
git clone https://github.com/abhishek-af8/CommandsMarkdownNotes.git
```
### 2. Open the cheat sheet:

1. Open the cloned folder in **VS Code**.
2. Open the `commands.md` file.
3. Press `Ctrl+Shift+V` to see a **beautiful Markdown preview**.

---

## Contributing

If you want to suggest improvements, updates, or add examples:

1. Fork the repository to your GitHub account.

2. Make your changes in your fork.

3. Open a Pull Request to this repository.

>Note: This repository is primarily a personal reference, but contributions are welcome if they improve clarity, organization, or usability.
