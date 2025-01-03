# zsh auto suggesstion

```bash
# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# zsh-256color
cd $ZSH_CUSTOM/plugins && git clone https://github.com/chrissicool/zsh-256color
```
- In the plugins

```
plugins=(
  git
  zsh-256color  
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```
- Config shortcut to accept the suggestion

```bash
nano .zshrc

# auto suggest
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=#B0EBB4,bg=#000000,bold"

# 
bindkey "^[[Z" magic-space            # shift-tab to bypass completion
bindkey "^I^I" autosuggest-accept     # tab + tab for accept the suggestion
```
