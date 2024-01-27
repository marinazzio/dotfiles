_Based on Atlassian [how-to](https://www.atlassian.com/git/tutorials/dotfiles)_

## Before cloning to a new system

```shell
alias dtf='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
echo ".dotfiles" >> .gitignore
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
