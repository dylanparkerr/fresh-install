----SYSTEM----
sudo dnf update
sudo dnf install alacritty gnome-tweaks 'google-roboto*'

git clone https://github.com/ryanoasis/nerd-fonts.git
./install.sh FiraCode

in tweaks
	interface: roboto regular 11
	document: roboto slab regular 11
	monospace: firacode nerd font medium 11
	legacy windows: roboto regular 11
	antialiasing: subpixel

settings > keyboard > view and customize shortcuts > custom shortcuts
	name: terminal
	command: env -u WAYLAND_DISPLAY alacritty
	shortcut: super + enter

----NVIM----
sudo dnf install neovim lazygit ripgrep nodejs

git clone --depth 1 https://github.com/wbthomason/packer.nvim\
 ~/.local/share/nvim/site/pack/packer/start/packer.nvim

git clone https://github.com/dylanparkerr/dotfiles.git

~/dev/dotfiles/scripts/update.sh fromrepotolocal
from init.lua - comment out caffine and configs
:PackerSync
uncomment out affine and configs

to install lsp servers
:Mason
    pyright, lua-language-server(sumneko-lua)

to install treesitter parsers
:TSInstall <language> (might have to install clang)
    python, lua

(look into go, js, rust, java, sql)


TODO lazygit install and config
----OTHER----
copy .bashrc from dotfiles
