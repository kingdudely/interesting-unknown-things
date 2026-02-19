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

# Installation scripts
* Xpra: http://xpra.org/get-xpra.sh
* Docker: https://get.docker.com
* Rev.ng: https://rev.ng/downloads/revng-distributable/master/install.sh
