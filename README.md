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
  brew install --with-default-names gnu-sed
  brew install coreutils
  omf install budspencer
  omf theme budspencer
  set budspencer_colors 000000 333333 666666 ffffff 2981c3 186ecc ff007d d81abe ff6600 da7f1c 29e4c5 18de74
  set -U budspencer_nogreeting
  set -U budspencer_no_cd_bookmark # https://github.com/oh-my-fish/theme-budspencer/issues/31
```

_Set [iTerm font to Powerline version](https://github.com/powerline/fonts/issues/44#issuecomment-300643099)_

Create `aliases.fish` file in `~/.config/fish/` to define custom aliases

Finally, in `~/.config/fish/config.fish`:

```sh
  . ~/.config/fish/aliases.fish # load aliases file
  status --is-interactive; and source (rbenv init -|psub) # automatically source rbenv

  if test (uname -s) = "Darwin"
    set -gx PATH /usr/local/opt/coreutils/libexec/gnubin $PATH
    set -gx PATH /usr/local/opt/gnu-sed/libexec/gnubin $PATH
  end
```

### Karabiner

Put `arrows.json` in `.config/karabiner/assets/complex_modifications/`
