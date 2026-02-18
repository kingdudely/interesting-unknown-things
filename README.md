# Github Codespaces
`lsblk` shows a 512 gigabyte drive that can be used for extra storage.
`docker` is logged into account `codespacesdev`.

# ChromeOS Crostini
To change the Linux distribution, open `Crosh` with <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>, and copy and paste this script:
```sh
# lxc stop penguin
lxc delete --force penguin
lxc remote add canonical-images https://images.lxd.canonical.com --protocol=simplestreams

read -p "Which image do you want to use? (e.g., alpine/3.20, ubuntu/latest): " IMAGE
lxc launch canonical-images:${IMAGE} penguin
lxc exec penguin -- /bin/sh
```
