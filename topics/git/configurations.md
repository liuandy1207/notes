# Git Configurations

## Config Levels
```shell
/etc/gitconfig        # system level, for all users
~/.gitconfig          # global level, for a specific user
PROJECT/.git/config   # local level, for a specific project named PROJECT

```

## Common Configurations
```git
git config --global user.name "GITHUB_USERNAME"
git config --global user.email "GITHUB_PASSWORD"
git config --global core.editor "TEXT_EDITOR"
git config --global color.ui true

git config --list        # display current config
```
