### Full Setup: Zsh Substring Search (Middle & Prefix)

1. **Remove broken repo (if added)**
```
sudo rm -f /etc/apt/sources.list.d/shells:zsh-users:zsh-history-substring-search.list
sudo rm -f /etc/apt/trusted.gpg.d/shells_zsh-users_zsh-history-substring-search.gpg
```

2. **Clone the plugin**
```bash
git clone https://github.com/zsh-users/zsh-history-substring-search "${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh/custom}}/plugins/zsh-history-substring-search"
```

3, **Add to .zshrc plugins**
```sh
nano ~/.zshrc
```

Ensure this line exists:
```
plugins=(git zsh-history-substring-search)
```

4. **Add key bindings (in .zshrc)**
```sh
bindkey '^[[A' history-substring-search-up
bindkey '^[[B' history-substring-search-down
bindkey '^[OA' history-substring-search-up
bindkey '^[OB' history-substring-search-down
```

Ensure no blocking variable is set Remove or comment this line in .zshrc if present:
`grep HISTORY_SUBSTRING_SEARCH_PREFIXED=1 ~/.zshrc`

Reload Zsh
```bash
exec zsh
```
