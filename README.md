# Dotfiles Configuration

This repository contains my personal dotfiles configuration for Neovim, Zsh, and SSH.

## 📁 Structure

```
dotfiles/
├── nvim/                    # Neovim configuration
│   ├── init.lua            # Main configuration entry point
│   ├── lua/anatolii_veselyi/
│   │   ├── plugins-setup.lua  # Plugin management with Packer
│   │   ├── core/
│   │   │   ├── options.lua    # Neovim options
│   │   │   ├── keymaps.lua    # Key mappings
│   │   │   └── colorscheme.lua # Color scheme configuration
│   │   └── plugins/           # Plugin-specific configurations
│   │       ├── lsp/           # LSP configurations
│   │       └── *.lua          # Individual plugin configs
│   └── plugin/
│       └── packer_compiled.lua # Packer compiled plugins
├── zsh/
│   └── .zshrc              # Zsh configuration
└── ssh/
    └── config              # SSH configuration
```

## 🚀 Neovim Configuration

### Core Setup
- **Package Manager**: Packer.nvim
- **Colorscheme**: vim-nightfly-guicolors
- **Leader Key**: Space (` `)

### Key Features
- **LSP Support**: Full Language Server Protocol support with Mason
- **Autocompletion**: nvim-cmp with multiple sources
- **Fuzzy Finding**: Telescope for file/text searching
- **File Explorer**: nvim-tree
- **Syntax Highlighting**: Treesitter
- **Git Integration**: Gitsigns
- **Statusline**: Lualine

### Essential Plugins
- `packer.nvim` - Plugin manager
- `nvim-lspconfig` - LSP configuration
- `mason.nvim` - LSP server management
- `nvim-cmp` - Autocompletion
- `telescope.nvim` - Fuzzy finder
- `nvim-tree.lua` - File explorer
- `nvim-treesitter` - Syntax highlighting
- `lualine.nvim` - Status line
- `gitsigns.nvim` - Git integration
- `Comment.nvim` - Commenting
- `vim-surround` - Surround text manipulation
- `nvim-autopairs` - Auto-close brackets/quotes

### Key Mappings

#### General
- `jk` - Exit insert mode
- `<leader>nh` - Clear search highlights
- `<leader>+` / `<leader>-` - Increment/decrement numbers

#### Window Management
- `<leader>sv` - Split window vertically
- `<leader>sh` - Split window horizontally
- `<leader>se` - Make split windows equal
- `<leader>sx` - Close current split

#### Tabs
- `<leader>to` - Open new tab
- `<leader>tx` - Close current tab
- `<leader>tn` - Next tab
- `<leader>tp` - Previous tab

#### Plugins
- `<leader>e` - Toggle file explorer (nvim-tree)
- `<leader>sm` - Toggle split window maximization
- `<leader>ff` - Find files (Telescope)
- `<leader>fs` - Live grep (Telescope)
- `<leader>fc` - Find string under cursor (Telescope)
- `<leader>fb` - List buffers (Telescope)
- `<leader>fh` - Help tags (Telescope)

### Configuration Options
- Relative line numbers enabled
- 2-space tabs with auto-indent
- No line wrapping
- Smart case search
- Cursor line highlighting
- System clipboard integration
- Split windows open right/below

## 🐚 Zsh Configuration

### Theme & Framework
- **Framework**: Oh My Zsh
- **Theme**: Powerlevel10k
- **Prompt**: Instant prompt enabled

### Plugins
- `git` - Git aliases and functions
- `zsh-autosuggestions` - Command suggestions
- `zsh-syntax-highlighting` - Syntax highlighting
- `web-search` - Web search from terminal

### History Configuration
- Removes duplicate entries
- Ignores commands starting with space
- Efficient history search

### Custom Aliases
- `ic` - Quick access to iCloud Drive (`cd ~/Library/Mobile\ Documents/com~apple~CloudDocs`)

### Environment
- **PATH**: Includes Rancher Desktop binaries
- **Editor**: Configuration ready for vim/nvim setup

## 🔐 SSH Configuration

### Features
- Legacy algorithm support for older systems
- Custom configurations for local network hosts
- Support for various cipher suites and key exchange algorithms

### Supported Hosts
- Multiple local network hosts (192.168.0.x range)
- Compatible with older SSH implementations

## 📦 Installation

### Prerequisites
- Neovim 0.8+ 
- Node.js (for LSP servers)
- Git
- Zsh
- Oh My Zsh
- Powerlevel10k theme

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone <repository-url> ~/dotfiles
   ```

2. **Neovim Setup**:
   ```bash
   # Create symlink or copy nvim config
   ln -s ~/dotfiles/nvim ~/.config/nvim
   
   # Open nvim and install plugins
   nvim
   # Run :PackerInstall
   ```

3. **Zsh Setup**:
   ```bash
   # Backup existing .zshrc
   mv ~/.zshrc ~/.zshrc.backup
   
   # Create symlink
   ln -s ~/dotfiles/zsh/.zshrc ~/.zshrc
   
   # Source the configuration
   source ~/.zshrc
   ```

4. **SSH Setup**:
   ```bash
   # Backup existing SSH config
   mv ~/.ssh/config ~/.ssh/config.backup
   
   # Create symlink
   ln -s ~/dotfiles/ssh/config ~/.ssh/config
   ```

## 🔧 Customization

### Adding New Plugins to Neovim
1. Add the plugin to `lua/anatolii_veselyi/plugins-setup.lua`
2. Create configuration file in `lua/anatolii_veselyi/plugins/`
3. Require the configuration in `init.lua`
4. Run `:PackerInstall`

### Modifying Keymaps
- Edit `lua/anatolii_veselyi/core/keymaps.lua`
- Changes take effect after restarting Neovim

### Zsh Customization
- Add aliases and functions to `.zshrc`
- Install additional Oh My Zsh plugins by adding to the `plugins` array

## 🚨 Troubleshooting

### Neovim Issues
- Run `:checkhealth` to diagnose problems
- Ensure LSP servers are installed via Mason (`:Mason`)
- Check plugin status with `:PackerStatus`

### Zsh Issues
- Verify Oh My Zsh installation
- Check if Powerlevel10k is properly installed
- Run `p10k configure` to reconfigure the theme

### SSH Issues
- Verify SSH key permissions (`chmod 600 ~/.ssh/id_rsa`)
- Test connections with `ssh -v <host>`

## 📝 Notes

- The configuration is optimized for macOS with Zsh
- LSP servers are managed through Mason for easy installation
- The setup includes sensible defaults for development work
- All configurations are modular and can be easily extended

## 🔄 Maintenance

- Regularly update plugins with `:PackerUpdate`
- Keep Oh My Zsh updated with `omz update`
- Review and update LSP servers through Mason
- Backup configurations before major changes

---

*Last updated: July 2025*
