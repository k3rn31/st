# ST
This is a fork of AUR _st_ package maintained by me. The original
package has been modified so that some patches will be applied upon
building it.
Currently applied patches are:
- `st-alpha`: add transparency to the terminal.
- `st-clipboard`: allow to interact with the clipboard
- `st-scrollback`: allow to scroll
- `st-xresources`: enable some Xresources configurations

For reference read [how to build and install Suckless Simple Terminal](https://brianbuccola.com/how-to-build-and-install-st-suckless-simple-terminal-from-source-on-arch-linux/).

## Add _aur_ remote
Upon first cloning, add _aur_ remote.**

```
git remote add aur https://aur.archlinux.org/st.git
```

## Rebase on the original AUR _st_
When the original AUR _st_ package gets updated, it is necessary to
_rebase_ onto the new HEAD and resolve merge conflicts.

```
$ git pull aur master --rebase
```

Update hashes to the `md5sums` array.
```
$ updpkgsums
```

## Rebuild the package
After the merge conflicts are resolved or other changes have been
applied, the package can be rebuilt.

```
$ makepkg -si
```

### Push to GitHub
Remember to commit and push to k3rn31/st.

```
$ git push origin master
```
