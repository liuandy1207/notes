## Config Levels
```shell
/etc/gitconfig        # System level (all users) config files are usually located here
~/.gitconfig          # Global level for each user, applies to all git repos for that user
PROJECT/.git/config   # Local level for a specific project

```

## Common Configurations
```shell
git config --global user.name "GITHUB_USERNAME"
git config --global user.email "GITHUB_PASSWORD"
git config --global core.editor "TEXT_EDITOR"
git config --global color.ui true

git config --list        # display current config
```
