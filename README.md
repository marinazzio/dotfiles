_Based on Atlassian [how-to](https://www.atlassian.com/git/tutorials/dotfiles)_

# Dotfiles (Bare Repo Setup)

This repository uses **separate branches** for different OS environments:

- `master`: Linux
- `windows`: Windows

## Before cloning to a new system

```powershell
function dtf {
    git --git-dir=$HOME\.dotfiles --work-tree=$HOME @args
}

echo ".dotfiles" >> $HOME\.gitignore
git clone --bare --branch windows git@github.com:marinazzio/dotfiles.git $HOME\.dotfiles
dtf checkout windows
dtf config --local status.showUntrackedFiles no
```

## Cloning

```shell
git clone --bare git@github.com:marinazzio/dotfiles.git $HOME/.dotfiles
dtf checkout
rm README.md
```

In case of error either backup conflicting files or delete them

## Post-configuring

```shell
dtf config --local status.showUntrackedFiles no
```

Use `dtf` instead of `git` for further dotfiles maintenance
