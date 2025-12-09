# Getting started

## Fork the repository

<p align="center">
  <img src="https://github.com/user-attachments/assets/82327bc5-331e-49af-8b5c-717f563b67d4" width="400" style="border-radius: 8px;">
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
cd build/
ninja
```
