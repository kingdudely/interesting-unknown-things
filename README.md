# Github Codespaces
* `lsblk` shows a 512 gigabyte drive that can be used for extra storage.
* Every blank codespace is automatically logged into Docker account `codespacesdev`.

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
* Decompile it to a `.c`/`.cpp`/`.bc`/`.ll`/`.o` file and use `Emscripten` to turn it into WASM like so: (don't forget to implement the imports).
* Lift it to a `.bc`/`.ll` file and use `llc` and `wasm-ld` to turn it into WASM like so:
```sh
llc -filetype=obj -mtriple=wasm32-unknown-unknown -march=wasm32 input.exe.bc -o output.o
wasm-ld file.o -o file.wasm --no-entry --export-all --allow-undefined
```

# Installation scripts
* Xpra: http://xpra.org/get-xpra.sh
* Docker: https://get.docker.com
* Rev.ng: https://rev.ng/downloads/revng-distributable/master/install.sh
* LLVM: https://apt.llvm.org/llvm.sh
