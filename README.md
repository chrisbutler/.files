# .files

## Fish

### Install [Fishshell](https://fishshell.com/), [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish), and [Fisher](https://github.com/jorgebucaran/fisher)
```sh
brew install fish
echo /usr/local/bin/fish | sudo tee -a /etc/shells # add to list of shells
chsh -s /usr/local/bin/fish # make default
curl -L https://get.oh-my.fish | fish
curl -sL https://git.io/fisher | source && fisher install jorgebucaran/fisher
```

### Install [powerline](https://github.com/powerline/fonts) fonts
Set [iTerm font to Powerline version](https://github.com/powerline/fonts/issues/44#issuecomment-300643099)

### Install `gnu-sed` and `coreutils`
These are required for the Budspencer theme to work correctly
```sh
brew install coreutils gnu-sed
```

### Fish config
Create `aliases.fish` file in `~/.config/fish/` to define custom aliases

Finally, in `~/.config/fish/config.fish`:

```sh
. ~/.config/fish/aliases.fish # load aliases file

if test (uname -s) = "Darwin"
  set -gx PATH /usr/local/opt/coreutils/libexec/gnubin $PATH
  set -gx PATH /usr/local/opt/gnu-sed/libexec/gnubin $PATH
end
```

### Set up [budspencer](https://github.com/oh-my-fish/theme-budspencer) theme:
```sh
omf install budspencer
omf theme budspencer
set budspencer_colors 000000 333333 666666 ffffff 2981c3 186ecc ff007d d81abe ff6600 da7f1c 29e4c5 18de74
set -U budspencer_nogreeting
set -U budspencer_no_cd_bookmark # https://github.com/oh-my-fish/theme-budspencer/issues/31
```

### Configure `rbenv` and `nvm` to work with Fish
```sh
fisher install rbenv/fish-rbenv
fisher install jorgebucaran/nvm.fish
```

_Note: The `nvm.fish` package does not support automatically sourcing `.nvmrc`. Set a global default with `set --universal nvm_default_version <version>`.

## Karabiner

Put `arrows.json` in `.config/karabiner/assets/complex_modifications/`
