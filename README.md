# .files

### Fish

Install [Fishshell](https://fishshell.com/) and [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)

```sh
  brew install fish
  echo /usr/local/bin/fish | sudo tee -a /etc/shells # add to list of shells
  chsh -s /usr/local/bin/fish # make default
  curl -L https://get.oh-my.fish | fish
```
_NOTE: Fish is [not compatible with nvm](https://github.com/creationix/nvm/issues/303)_

Install [powerline](https://github.com/powerline/fonts) font pack and set up [budspencer](https://github.com/oh-my-fish/theme-budspencer) theme:

```sh
  omf install budspencer
  brew install --with-default-names gnu-sed
  brew install coreutils
  omf theme budspencer
```

Create `aliases.fish` file in `~/.config/fish/` to define custom aliases

Finally, in `~/.config/fish/config.fish`:

```sh
  . ~/.config/fish/aliases.fish # load aliases file
  status --is-interactive; and source (rbenv init -|psub) # automatically source rbenv
  set PATH /usr/local/opt/coreutils/libexec/gnubin $PATH # use expr from coreutils
```
