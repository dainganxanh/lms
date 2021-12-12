# 💻 Ubuntu Linux

## Basic commands

```
sudo apt update 
sudo apt upgrade
```

### Bộ gõ tiếng Việt ibus-bamboo

```
sudo apt update
sudo apt install ibus-bamboo
```

Gỡ bỏ:

```
sudo apt remove ibus-bamboo
sudo apt autoclean && sudo apt autoremove
```

## Text editor

```
// Dùng Sublime Text quyền sudo: 
suso subl <file>

// Dùng vim hay nano cũng tương tự
```

## Cài Chrome và Chrome remote desktop

### Cài Chrome trên ubuntu 20.04

```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

### Cài Chrome remote desktop

```
wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb -P /tmp
sudo apt install /tmp/chrome-remote-desktop_current_amd64.deb

# Tạo folder và chmod quyền đọc ghi
sudo mkdir ~/.config/chrome-remote-desktop
sudo chmod -R 777 ~/.config/chrome-remote-desktop

# Cài thêm lsde nếu run default bị màn hình đen 
sudo apt install  lxde
```



## Lỗi hay gặp

#### Lỗi Authentication required to refresh system repositories

Lỗi này thường phát sinh sau khi cài remote desktop

```
sudo usermod -a -G adm <username>
sudo usermod -a -G sudo <username>
```

