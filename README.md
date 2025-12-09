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
# nmtui 

- Connect wifi

```zsh
❯ nmcli connection show
NAME                UUID                                  TYPE      DEVICE          
HUY_HOANG_Lau2_3    5b26e077-a2ff-4498-b1e5-f0eb4f8bcfc6  wifi      wlp1s0          
CloudflareWARP      79d5bd09-304a-4a99-b7c7-23a044def9f2  tun       CloudflareWARP  
br-7a202b6c40ee     8ee1e7b4-5d1f-45df-be68-8f7840c96e26  bridge    br-7a202b6c40ee 
lo                  9bb33b11-29f2-4441-b259-30f7d1cdd7c5  loopback  lo              
docker0             0ef73a90-6b33-47b3-8627-f3f70e6e632c  bridge    docker0         
Wired connection 1  7cffa651-f507-4ddd-ab4d-b1a3b7fa3f5d  ethernet  --  
```

- Establish new connection

```zsh
❯ sudo nmcli dev wifi connect "HUY_HOANG_Lau2_3" password "<password>" name "<hihi>" --ask

# Verify, password above need to match with nmconnection:psk=<password>
sudo grep -R "psk" /etc/NetworkManager/system-connections

#/etc/NetworkManager/system-connections/HUY_HOANG_Lau2_3.nmconnection:key-mgmt=wpa-psk
#/etc/NetworkManager/system-connections/HUY_HOANG_Lau2_3.nmconnection:psk=<password>
```

- Delete a connection

```zsh
nmcli connection delete HUY_HOANG_Lau2_3
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
