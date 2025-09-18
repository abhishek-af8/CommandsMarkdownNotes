# CommandsMarkdownNotes

A **personal Linux, WSL, Git, and GCC commands cheat sheet** for quick reference and learning.  
This repository contains my curated `commands.md` file, organized to help with navigation, file management, Git workflows, and compilation processes.

---

## Table of Contents

- [Linux Command Cheat Sheet](commands.md#linux-command-cheat-sheet)
  - [Symbols (VS Code Snippet Prefixes)](commands.md#symbols-vs-code-snippet-prefixes)
  - [Compilation & Execution](commands.md#compilation--execution)
  - [Navigation](commands.md#navigation)
  - [File Management](commands.md#file-management)
  - [Directory Management](commands.md#directory-management)
  - [Navigation Shortcuts](commands.md#navigation-shortcuts)
  - [Backup & Transfer (WSL ↔ Windows)](commands.md#backup--transfer-wsl-↔-windows)
    - [WSL → Windows](commands.md#wsl-→-windows)
    - [Windows → WSL](commands.md#windows-→-wsl)
  - [Git: Backing Up Specific Folders](commands.md#git-backing-up-specific-folders)
    - [Case 1: Upload only `SystemCalls/`](commands.md#case-1-upload-only-systemcalls)
    - [Case 2: Upload both `SystemCalls/` and `Linking/`](commands.md#case-2-upload-both-systemcalls-and-linking)
    - [Case 3: Exclude everything except `SystemCalls/` and `Linking/`](commands.md#case-3-exclude-everything-except-systemcalls-and-linking)
  - [Git Update/Push Workflow](commands.md#git-updatepush-workflow)
  - [Git enhancements](commands.md#git-enhancements)
  - [Git Pull & Merge Notes (Collaboration & Safety)](commands.md#git-pull--merge-notes-collaboration--safety)
    - [Why Pull Before Push](commands.md#why-pull-before-push)
    - [What `git pull origin main` Does](commands.md#what-git-pull-origin-main-does)
    - [Why Conflicts Happen](commands.md#why-conflicts-happen)
    - [Types of Merges](commands.md#types-of-merges)
    - [Step-by-Step Collaborative Workflow](commands.md#step-by-step-collaborative-workflow)
  - [GCC Compilation Phases & Commands](commands.md#gcc-compilation-phases--commands)
    - [Preprocessing (C → Preprocessed C)](commands.md#preprocessing-c-→-preprocessed-c)
    - [Compilation (C/Preprocessed C → Assembly)](commands.md#compilation-cpreprocessed-c-→-assembly)
    - [Assembly (Assembly → Object Code)](commands.md#assembly-assembly-→-object-code)
    - [Linking (Object Files → Executable)](commands.md#linking-object-files-→-executable)
  - [Tips](commands.md#tips)


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
