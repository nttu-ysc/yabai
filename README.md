# Yabai & Skhd Configuration

## Installation

```bash
# Install yabai, skhd, jq
$ brew install yabai
$ brew install skhd
$ brew install jq

# If there are previous config, remove them.
$ rm -f "${HOME}"/.{yabai,skhd}rc

# Clone config to local
$ git clone https://github.com/nttu-ysc/yabai "${HOME}/.config/yabai"
$ ln -s "${HOME}/.config/yabai/yabai/yabairc" "${HOME}/.yabairc"
$ ln -s "${HOME}/.config/yabai/yabai/skhdrc" "${HOME}/.skhdrc"

# Start yabai & skhd
$ brew services start yabai
$ brew services start skhd


# --- (options) Install Janky border start ---
# repo: https://github.com/FelixKratz/JankyBorders

# Install borders
$ brew tap FelixKratz/formulae
$ brew install borders

# Clone config
$ ln -s "${HOME}/.config/yabai/border/bordersrc" "${HOME}/.config/borders/bordersrc"

# Start borders
$ brew service start FelixKratz/formulae/borders

# --- Install Janky border end ---

# --- (options) Install stackline start ---

# Install stakline
$ brew install hammerspoon --cask
$ git clone https://github.com/AdamWagner/stackline.git ~/.hammerspoon/stackline
$ cp ~/.hammerspoon/stackline/conf.lua ~/.hammerspoon/stakeline_config.lua

# **Hint**: If your mac is M1 structure - you have to change the code below
# -- in stackline/conf.lua
# c.paths.yabai = '/opt/homebrew/bin/yabai' -- silicon mac, M1
# c.paths.yabai = '/usr/local/bin/yabai'    -- intel version.

$ cd ~/.hammerspoon
$ echo 'stackline = require "stackline"' >> init.lua
$ echo 'local stackline_config = require "stackline_config"' >> init.lua
$ echo 'stackline:init(stackline_config)' >> init.lua

# --- Install stackline end ---

```