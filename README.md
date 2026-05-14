# Ak47 Lua Configuration

Built configuration for easy `nvim` setup. Minimalistic.

## TLDR
Run this command `git clone https://github.com/mohit2530/ak47-lua-config ~/.config/nvim`.

Everything should just work out of the box.

## Installation (New Machine)

### macOS

`brew install neovim`

`brew install ripgrep`

`brew install fzf`

Download git autocomplete and set up `echo 'autoload -Uz compinit && compinit' >> ~/.zshrc && . ~/.zshrc`

### Linux (Ubuntu/Debian)
sudo apt update
sudo apt install neovim ripgrep fzf xclip

## Clone Config
`git clone https://github.com/mohit2530/ak47-lua-config ~/.config/nvim`

## Clipboard Setup (IMPORTANT)
### macOS
Clipboard works automatically.

### Linux (required)

`sudo apt install xclip`


### Neovim clipboard config (lua/core/clipboard.lua)

vim.opt.clipboard = "unnamedplus"

This enables:

y → system clipboard
d → system clipboard
p → system clipboard
Manual fallback (always works)
"+y   " copy to system clipboard
"+p   " paste from system clipboard

### Keymaps (Core Behavior)

lua/core/keymaps.lua

-- Hover documentation (LSP)
vim.keymap.set("n", "K", vim.lsp.buf.hover)

-- Go to definition
vim.keymap.set("n", "gd", vim.lsp.buf.definition)

-- File explorer (if using netrw)
vim.keymap.set("n", "<leader>e", ":Ex<CR>")

### Fuzzy File Search (fzf / telescope)
Recommended: Telescope

lua/plugins/telescope.lua

vim.keymap.set("n", "<leader>ff", "<cmd>Telescope find_files<cr>")
vim.keymap.set("n", "<leader>fg", "<cmd>Telescope live_grep<cr>")

#### Dependencies:

`brew install ripgrep`

## Portability Rule

On every new machine:

git clone <repo> ~/.config/nvim

Then install:
```
neovim
ripgrep
fzf
xclip (linux only)
```

