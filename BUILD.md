# Getting started

## Fork the repository and copy fork's repo link

<p align="center">
  <img src="https://github.com/user-attachments/assets/e15a45f7-b567-4af0-975b-1712d0395b28" width="400" style="border-radius: 8px;">
</p>

## Clone the repository

```bash
# specify github username
USERNAME="your_github_username_here"
git clone git@github.com:${USERNAME}/serenedb.git
cd serenedb
git remote add upstream git@github.com:serenedb/serenedb.git
git submodule update --init --recursive
```

## Build

Use cmake with preset 'lldb' to build it in debug. Additional build presets are defined in `CMakePresets.json` file.

```
# from the root of the repository
cmake --preset lldb
```
