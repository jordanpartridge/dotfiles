# dotfiles

Cross-platform dotfiles managed with [chezmoi](https://chezmoi.io).

Works on: **Nobara Linux** | **macOS**

## Quick Install

```bash
# One-liner (creates ~/.local/share/chezmoi and applies)
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply jordanpartridge
```

Or step by step:
```bash
# Install chezmoi
sh -c "$(curl -fsLS get.chezmoi.io)" -- -b ~/.local/bin

# Clone and apply
chezmoi init jordanpartridge
chezmoi apply
```

## What's Included

| File | Purpose |
|------|---------|
| `.zshrc` | Zsh config with zinit, aliases, fzf |
| `.gitconfig` | Git with delta, aliases |
| `.vimrc` | Pretty vim for git commits |
| `.config/starship.toml` | Catppuccin Macchiato prompt |

## Dependencies

### Linux (Fedora/Nobara)
```bash
sudo dnf install zsh starship bat fd-find fzf ripgrep git-delta
sudo dnf copr enable atim/lazygit && sudo dnf install lazygit
cargo install eza
```

### macOS
```bash
brew install zsh starship eza bat fd fzf ripgrep git-delta lazygit
```

## Post-Install

```bash
# Set zsh as default shell
chsh -s $(which zsh)

# Restart terminal or:
exec zsh
```

## Customization

Local overrides (not synced):
- `~/.zshrc.local` - Machine-specific shell config
- `~/.gitconfig.local` - Machine-specific git config

## Update

```bash
chezmoi update
```

## License

MIT
