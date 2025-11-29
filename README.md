# stuffs
- zoxide, exa, fzf, duf, htop, btop, fastfetch, cmatrix
```zsh
sudo apt-get install zoxide exa fzf duf htop btop fastfetch cmatrix
```
- For zoxide
```zsh
eval "$(zoxide init zsh)"
```

# oh-my-zsh

- https://ohmyz.sh/#install

```zsh
sudo apt-get install zsh curl  && sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

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

# xclip

- https://linuxconfig.org/how-to-use-xclip-on-linux

```bash
# xclip
alias xc='xclip'
alias xcsc='xclip -selection clipboard'
```

# warp client

- https://developers.cloudflare.com/warp-client/get-started/linux/

```zsh
# Debian 13 Trixe
# 1) Thêm repository Cloudflare chuẩn cho Debian
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg | sudo tee /etc/apt/keyrings/cloudflare-warp.asc >/dev/null

# Thêm repo:
echo "deb [signed-by=/etc/apt/keyrings/cloudflare-warp.asc] https://pkg.cloudflareclient.com trixie main" | \
sudo tee /etc/apt/sources.list.d/cloudflare-warp.list

# 2) Update lại danh sách package
sudo apt update

# 3) Cài Warp
sudo apt install cloudflare-warp
```
