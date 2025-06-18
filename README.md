# Ubuntu WSL Dotfiles

## Introduction

This is a repository for my Ubuntu WSL dotfiles, for version control on my configurations. I aim for my setup to be simple and focus on function while still making it bearable to look at on long periods of time. Using these configurations I have setup a specific workflow:

* Use Windows terminal, style and colors are from the terminal
* Use tmux for multiple terminal usage (splitting/tabs)
* Use VSCode Remote for development and scripting
* Use terminal Vim only for simple actions and reading files

This is why my dotfiles do not include Windows terminal configurations, or terminal-focused development tools such "Neovim". The included configurations are:

* zsh
* vim
* fastfetch
* starship
* tmux

## Gallery

![Windows Terminal Screenshot](https://github.com/user-attachments/assets/87b89209-65dd-4d87-a2c1-bda85929ce99)

## Setup

### Enjoy Rose Pine Moon

For every configuration not listed below, most likely I'm using a theme from https://rosepinetheme.com/, specifically the **Rose Pine Moon** variant. This includes:
* Windows Terminal
* btop

### Install a Nerd Font

A nerd font allows special icons to be used in your terminal. You can get these special fonts at https://www.nerdfonts.com/. Personally I use `Iosevka Nerd Font` because it looks very compact.

### Install vim, and the plugin manager

Vim motions are still the greatest blessing for text editing with efficiency. Use these commands to install `vim` and `vim-plug`:

```sh
apt install vim
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Don't forget to `:PlugInstall` after getting my Vim configuration.

### Install rust, and important binaries related

Rust provides some useful tools to modify my shell usage, for example `eza` replaces `ls` for a fast and visually appealing `ls`, and `starship` modifies the look of the command prompt of the shell. Use these commands to setup:

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo install eza
cargo install starship
```

### Install zoxide

Zoxide replaces `cd` and makes navigation in the terminal extremely easy, because it allows for "directory teleportation" using fuzzy finding on your directory change history, use this command to install:

```sh
curl -sSfL https://raw.githubusercontent.com/ajeetdsouza/zoxide/main/install.sh | sh
```

### Install tmux, and setup the plugin manager

Instead of relying on a builtin terminal split, I opted to use `tmux` because the configuration is very portable and is very easy to set up (with plugins too!), use these commands to install:

```sh
apt install tmux
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

You can read more on [how tmux works](https://github.com/tmux/tmux/wiki) and all the keybinds in the configuration file given. This includes learning [how to use the tmux plugin manager (tpm)](https://github.com/tmux-plugins/tpm).

### Install zsh, and change shell to zsh

Zsh is a very customizable shell, filled with easy ways to download extra extensions.

```sh
apt install zsh
chsh
```

### Install yadm, to easily clone my dotfiles

YADM (Yet Another Dotfiles Manager) can be used to easily clone dotfiles like Git, it's simply a repository hosted on your home directory.

```sh
yadm clone https://github.com/wintertia/ubuntu-wsl-dotfiles.git
```
