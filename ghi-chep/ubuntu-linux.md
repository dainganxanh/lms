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

### Sublime Text

```
// Dùng SublimTex quyền sudo: 
suso subl <file>
```

## Lỗi hay gặp

#### Lỗi Authentication required to refresh system repositories

```
sudo usermod -a -G adm <username>
sudo usermod -a -G sudo <username>
```

