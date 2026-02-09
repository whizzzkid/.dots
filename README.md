# .dots
A simpler concise .dotfiles

## Installation

This is the simplest way to install the dotfiles.

### Manual

```
git clone --bare --depth 1 git@github.com:whizzzkid/.dots.git $HOME/.dots;
config config --local status.showUntrackedFiles no;
config checkout -f
```

### Automatic
```sh
dotfiles_init() {
    git --no-replace-objects clone --bare --depth 1 git@github.com:whizzzkid/.dots.git $HOME/.dots;
    config config --local status.showUntrackedFiles no;
    config checkout -f
}
```

## Configuration Management

### Adding New Configs

```sh
config add /path/to/config
config commit -m "commit message"
```

### Automatic Updates for existing configs

```sh
dotfiles_autoupdate() {
    config add -u && \
    config commit -m "Update $(date +"%Y-%m-%d %H:%M") $(uname -s)/$(uname -m)-$(hostname -s)" && \
    config push
}
```

### Status

```sh
config status
```

## Credits

- [CodeVoid](https://home.codevoid.de/posts/2019-04-27_Manage_dotfiles_with_git.html)

## License

[GPLv3](LICENSE)
