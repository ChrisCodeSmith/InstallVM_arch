# Arch

## Useful Links

- [VMware/Install Arch Linux as a guest](https://wiki.archlinux.org/title/VMware/Install_Arch_Linux_as_a_guest)

## Installation

- [Arch Install Scripts](https://wiki.archlinux.de/title/Arch_Install_Scripts)
- Remember to install vim, dhcpd, etc

A bit more detailed, for installing Arch on a VM, have a look into this [tutorial](https://cyberblogspot.com/how-to-install-arch-linux-on-vmware-workstation-player/).

## Networking (after booting into the new machine)
Edit `/etc/systemd/network/ens33.network`:

```
[Match]
Name=ens33
[Network]
DHCP=ipv4
```

Also give your `/etc/resolv.conf` a dns server.
And finalize the config:

```
systemctl start systemd-networkd
systemctl enable systemd-networkd
```


## Post Installation

- [Sudo](https://wiki.archlinux.org/title/sudo)
- [Pacman] (https://wiki.archlinux.org/title/pacman)
- [AUR](https://wiki.archlinux.org/title/Arch_User_Repository)


## Configuration

### Some important packages

```
pacman -S git rustup curl net-tools open-vm-tools xf86-input-vmmouse xf86-video-vmware mesa man-db man-pages firefox
```

#### Guides

- [Rust](https://wiki.archlinux.org/title/rust)

### Way to Graphical Desktop

#### Display Server: xorg

- `pacman -S xorg-server xorg-xinit`

#### Display Manager(/greeter):

- Lemurs: Get it via AUR: [lemurs-git](https://aur.archlinux.org/packages/lemurs-git) 
- See [official git repo](https://github.com/coastalwhite/lemurs) for further instructions

#### Window Manager: i3
[Arch i3 wiki](https://wiki.archlinux.org/title/i3), [i3 homepage](https://i3wm.org)

- `pacman -S i3 dmenu`

To get vmware copy&paste working, edit `~/.config/i3/config`and append:
```
exec --no-startup-id vmware-user
```

### Alacritty

- `pacman -S alacritty`

### Zsh
- `pacman -S zsh`
- [Oh My ZSH!](https://ohmyz.sh/#install)

### Tmux

- `pacman -S tmux`

### Neovim
