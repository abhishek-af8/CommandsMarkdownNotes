### Beautiful preview of commands.md
Press `ctrl+shift+V` to see a clear preview after editing.

# Linux Command Cheat Sheet

## Symbols (VS Code Snippet Prefixes)
- `rarrow` (→) Right Arrow
- `larrow` (←) Left Arrow
- `uarrow` (↑) Up Arrow
- `darrow` (↓) Down Arrow
- `dbarrow` (↔) Double Arrow
- `swap` (⇄) Swap Arrow
- `rdarrow` (⇒) Right Double Arrow
- `lrharpoon` (↦) Left-Right Harpoon
- `rhook` (↪) Right Hook Arrow
- `and` (∧) Logical AND
- `or` (∨) Logical OR
- `not` (¬) Logical NOT
- `forall` (∀) Universal Quantifier
- `exists` (∃) Existential Quantifier
- `in` (∈) Element Of
- `notin` (∉) Not Element Of
- `subset` (⊂) Subset of
- `supset` (⊃) Superset of
- `union` (∪) Union
- `inter` (∩) Intersection
- `sum` (∑) Summation
- `prod` (∏) Product
- `inf` (∞) Infinity
- `approx` (≈) Approximately Equal
- `neq` (≠) Not Equal
- `angle` (∠) Angle
- `prop` (∝) Proportional To
- `partial` (∂) Partial Differential
- `cplus` (⊕) Circle Plus
- `ctimes` (⊗) Circle Times




## Compilation & Execution
- `gcc a.c` → compile a.c into a.out
- `g++ a.cpp` → compile a.cpp into a.out
- `./a.out` → execute the compiled program
- `g++ file1.cpp file2.cpp -o output` → Compile multiple files into `output`
- `./output` → Run the compiled program



## Navigation
- `cd <directory>` → move into a directory
- `cd ..` → move back to parent directory
- `pwd` → show current directory path


## File Management
- `touch <filename>` → create a file
- `rm <filename>` → delete a file
- `mv <source> <destination>` → move/rename a file
- `cp <source> <destination>` → copy a file


## Directory Management
- `mkdir <dirname>` → create a directory
- `rmdir <dirname>` → remove empty directory
- `rm -r <dirname>` → remove directory and contents
- `rm -rf <folder_name>` → Delete a folder (recursively)


## Navigation Shortcuts
- `cd ~` → Go to WSL home folder (`/home/abhishek`)
- `cd /home/abhishek` → Explicitly go to home
- `pwd` → Show current location
- `cd -` → Go back to the previous directory
- `cd /mnt/c/...` → Access Windows C: drive from WSL
- `cd /mnt/d/...` → Access Windows D: drive from WSL


## Backup & Transfer (WSL ↔ Windows)

#### WSL → Windows
- `cp -r <folder_in_WSL> /mnt/d/<backup_folder>` → Copy a folder from WSL to D drive  
>Example: `cp -r ~/programs/Cpp/exec /mnt/d/Cpp/` → used to copy exec folder from WSL into CPP folder in D

- `cp -r <folder_in_WSL> /mnt/c/<backup_folder>` → Copy a folder from WSL to C drive

#### Windows → WSL
- `cp -r /mnt/d/<source_folder> ~/<destination_folder>` → Copy from D drive to WSL  
- `cp -r /mnt/c/<source_folder> ~/<destination_folder>` → Copy from C drive to WSL


# Git: Backing Up Specific Folders

### Case 1: Upload **only `SystemCalls/`** to GitHub
```bash
cd ~/programs/SystemCalls
git init
git add .
git commit -m "Initial commit for SystemCalls"
git branch -M main
git remote add origin <your-repo-URL>
git push -u origin main
```
### Case 2: Upload **both `SystemCalls/` and `Linking/`** to GitHub
1. Initialize Git in the parent `programs/` folder:
```bash
cd ~/programs
git init
git add Linking SystemCalls
git commit -m "Add Linking and SystemCalls"
git branch -M main
git remote add origin <your-repo-URL>
git push -u origin main
```
### Case 3: Exclude everything except `SystemCalls/` and `Linking/`
1. Create a `.gitignore` inside `programs/` with:
```yaml
# Ignore everything
*

# Allow Linking and SystemCalls
!Linking/
!SystemCalls/
```
2. Then, run this:
```bash
cd ~/programs
git add .
git commit -m "Track only Linking and SystemCalls"
git push -u origin main

```

# Git Update/Push Workflow
If I am updating my programs in my `SysCallsAndLinking` folder **[e.g., I added a `fork13.c` file into the `fork` folder in `SystemCalls`]**, this is the way to update the associated GitHub repo:

```bash
# Navigate to your repo folder
cd ~/programs/SysCallsAndLinking

# 1️ Check current status of repo
git status

# 2️ Pull latest changes from remote (avoids conflicts)
git pull origin main

# 3️ Stage only the specific file (safe way)
git add SystemCalls/fork/fork13.c

# OR stage all new/updated files (respects .gitignore)
git add .

# 4️ Commit with a descriptive message
git commit -m "Update: Added <filename> in <folder>"

# 5️ Push changes to GitHub main branch
git push origin main
```

# Git enhancements
 - Check repository status
 ```bash
 git status
 ```
  - Pull latest changes
 ```bash
 git pull origin main
 ```
  - Remove file from tracking
 ```bash
 git rm --cached <filename>
 ```
  - Stage specific file(s)
 ```bash
 git add <file1> <file2>
 ```
  - Commit with descriptive message
 ```bash
 git commit -m "Describe your changes here"
 ```
  - Push changes to remote
 ```bash
 git push origin main
 ```

# Git Pull & Merge Notes (Collaboration & Safety)

### 1️ Why Pull Before Push
- Pulling ensures your local branch is **up-to-date with remote**.
- Without pulling, you risk overwriting **new commits on GitHub**.
> Example: Suppose you add `fork13.c` locally, while at the same time Ashutosh has already updated `fork3.c` and pushed it to GitHub. 
  If you try to push your changes **without first pulling**, your local branch is **behind the remote branch** because it does not include Ashutosh’s new commit. 
  Git will reject your push to prevent accidentally **overwriting or “losing” Ashutosh’s update**. 
  In other words, if Git allowed the push, your older version of `fork3.c` (from before Ashutosh’s changes) would replace the newer version on GitHub, potentially breaking code or undoing important fixes. 
  Pulling first ensures your branch incorporates the remote updates safely before you add your own changes like `fork13.c`.


---

### 2️ What `git pull origin main` Does
`git pull origin main` = **fetch + merge**

1. **Fetch phase (`git fetch`)**
   - Downloads **all new commits, branches, tags** from remote GitHub.
   - Does **not change your working files yet**.
   - Git now knows about remote commits your local branch doesn’t have.

2. **Merge phase (`git merge`)**
   - Integrates the remote changes into your current branch.
   - **No conflicts:** changes in different files → auto-merge.
   - **Conflict:** same file/lines edited → Git asks you to resolve manually.

---

### 3️ Why Conflicts Happen
- Conflict occurs when **the same lines in a file** were changed locally and remotely.
- Git cannot decide which version to keep.
- You manually choose one or combine changes.

---

### 4️ Types of Merges

1. **Fast-forward merge**
   - Your local branch has no new commits.
   - Remote branch has new commits.
   - Git simply moves your local branch pointer forward to match remote. ✅
   - Example: Only Ashutosh updated fork3.c, you didn’t touch it → fast-forward merge.

2. **Three-way merge**
   - Both local and remote have **different new commits**.
   - Git compares **base commit → local → remote** and merges changes.
   - Conflicts may occur → manual resolution needed.

---

### 5️ Step-by-Step Collaborative Workflow
```bash
# 1️ Pull latest changes from GitHub
git pull origin main
# Updates fork3.c or any other files updated remotely

# 2️ Stage your new file(s)
git add SystemCalls/fork/fork13.c

# 3️ Commit locally
git commit -m "Added fork13.c"

# 4️ Push changes safely to GitHub
git push origin main
```


# GCC Compilation Phases & Commands

### 1. Preprocessing (C → Preprocessed C)
```bash
gcc -E main.c -o main.i
gcc -E sum.c -o sum.i
```
### 2. Compilation (C/Preprocessed C → Assembly)
```bash
gcc -S main.c -o main.s
gcc -S sum.c -o sum.s
```
### 3. Assembly (Assembly → Object Code)
```bash
gcc -c main.c -o main.o
gcc -c sum.c -o sum.o
```
### 4. Linking (Object Files → Executable)
```bash
gcc main.o sum.o -o main
```


## Tips
- `~` in WSL → Your home directory (`/home/<your_username>`)  
- Access Windows drives via `/mnt/c/` or `/mnt/d/`  
- Snippets: Use `Tab` to expand VS Code symbols (e.g., `dbarrow` for  ↔)
- Always `git pull` before starting new work in a shared repo to reinforce good practice.