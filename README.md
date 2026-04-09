# Github Codespaces
* `lsblk` shows a 512 gigabyte drive that can be used for extra storage.
* Every blank codespace is automatically logged into Docker account `codespacesdev`.
* To run Windows in GitHub codespaces, click on [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/dockur/windows?devcontainer_path=.devcontainer%2F210+-+Tiny10%2Fdevcontainer.json&machine=standardLinux32gb) (or use CodeAnywhere)

# ChromeOS
* To open `Crosh`, do <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.
* To enter terminal mode in `Crosh`, run
```sh
vmc start termina
```
* To use a Linux distribution in `Crosh` terminal mode, find the one you want with
```sh
lxc list
```
and then do
```sh
lxc exec CONTAINER_NAME_HERE -- /bin/sh
```
* [How to fix Crostini crashing immediately](https://support.google.com/chromebook/thread/415077886/after-the-latest-update-i-cannot-start-linux-even-after-a-powerwash?hl=en&utm_source=chatgpt.com):
> When you open terminal try clicking on the 'manage' button, then back.  This works for me, for now. If they do not fix this issue I am concerned even this will not work....then I will have to move from chromebook for my work program! Not what I want. 
Good luck, hope it works for you
(I believe my issue started with the version before what you listed)

* To install a new Linux distribution in `Crostini`, open `Crosh` terminal mode, and then copy and paste this script:
<!--
lxc stop penguin
lxc delete --force penguin
-->
```sh
lxc remote add canonical-images https://images.lxd.canonical.com --protocol=simplestreams
lxc launch canonical-images:IMAGE_NAME_HERE CONTAINER_NAME_HERE
```

# Native binary/executable to WASM methods
* Decompile it to a `.c`/`.cpp`/`.bc`/`.ll`/`.o` file and use `Emscripten` to turn it into WASM (don't forget to implement the imports).
* Lift it to a `.bc`/`.ll` file and use `llc` and `wasm-ld` to turn it into WASM like so:
```sh
llc -filetype=obj -mtriple=wasm32-unknown-unknown -march=wasm32 file.bc -o file.o
wasm-ld file.o -o file.wasm --no-entry --export-all --allow-undefined
```

# Installation scripts
* Xpra: http://xpra.org/get-xpra.sh
* Docker: https://get.docker.com
* Rev.ng: https://rev.ng/downloads/revng-distributable/master/install.sh
* LLVM: https://apt.llvm.org/llvm.sh
* RustUp: https://sh.rustup.rs

# Roblox
* ![image](https://github.com/user-attachments/assets/007f1a0c-551f-4a1b-b721-fe348448e4c8)

