# 🔍 Validation Git Hooks (Lefthook-based)

This template sets up a cross-platform Git `pre-commit` hook using Lefthook to validate the following things:

- Validate that committed files do not contain UTF-8 BOMs — except for extensions where BOMs are expected.
  - Allows `.csproj`, `.resx`, `.ps1`, image and binary files to bypass
  - Flags `.csv`, `.js`, `.ts`, `.svg`, etc. if they contain a BOM
- Validate that committed files have lines not longer than 120 characters (or whatever is configured inside the `.editorconfig` file) — except for files where longer lines can be expected (e.g. Markdown files).
  - Allows text files and some others (like `.csv`) files to bypass
  - Flags other files if they contain lines exceeding 120 characters (or whatever is configured inside the `.editorconfig` file)

## ✅ What It Does

- Checks staged files on commit
- Checks the Operating System
- Runs scripts tailored for each system by using a runner script (`.ps1` for PowerShell, `.sh` for Linux/MacOS)

## 🛠️ Setup Instructions

## 1. Install Lefthook for your operating system:

- Follow the instructions [from this page](https://lefthook.dev/installation/index.html).

## 2. Run:

### On Linux/MacOS

   ```bash
   lefthook install
   ```

### On Windows

   ```PowerShell
   lefthook install
   ```

## 2. Try committing a file with a BOM, or with lines longer than 120 characters — the hook will block it.

### 🧪 Manual Test
```bash
lefthook run pre-commit
```

## 👷 Supported Platforms
- ✅ Windows (via PowerShell/CMD)
- ✅ macOS / Linux (via Bash)
