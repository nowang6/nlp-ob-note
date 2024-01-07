
# 文本处理命令

```bash
wc -l train_data.csv #查看行总数
head -10 train_data.csv #查看前10行
cat train_data.csv | cut -f2,4 -d"," | more # 查看第2列到第4列，分隔符为逗号
split -l 10000 -d -a3 train_data.csv train0 #切割文件，每个文件1万行，输出为train0xxx
```

# 安装

## 包管理

```bash
/etc/apt/apt.conf.d/proxy.conf

mount -o loop /data/debian-12.4.0-amd64-DVD-1.iso /media/cdrom

```

## shell 和插件

```bash
apt install zsh
#将 zsh 设置为默认 Shell
chsh -s /bin/zsh
```

安装 on my zsh
```bash
download ohmyzsh-master
mv  ohmyzsh-master ~/.oh-my-zsh
download install-oh-my-zsh.sh from https://gist.github.com/hewerthomn/65bb351bf950470f6c9e6aba8c0c04f1
./install-oh-my-zsh.sh

```

安装主题和插件

```bash
wget --no-check-certificate  https://github.com/zsh-users/zsh-autosuggestions/archive/refs/heads/master.zip
mv zsh-autosuggestions-master .oh-my-zsh/plugins/zsh-autosuggestions

wget --no-check-certificate  https://github.com/romkatv/powerlevel10k/archive/refs/heads/master.zip
mv powerlevel10k .oh-my-zsh/custom/themes/powerlevel10k

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`

export TERM=xterm-256color

```


# 环境
## 安装包
/etc/apt/apt.conf.d/proxy.conf

## 安装shell

```bash
apt install zsh
#将 zsh 设置为默认 Shell
chsh -s /bin/zsh
```

安装 on my zsh
```bash
download ohmyzsh-master
mv  ohmyzsh-master ~/.oh-my-zsh
download install-oh-my-zsh.sh from https://gist.github.com/hewerthomn/65bb351bf950470f6c9e6aba8c0c04f1
./install-oh-my-zsh.sh

```


安装主题和插件

```bash
wget --no-check-certificate  https://github.com/zsh-users/zsh-autosuggestions/archive/refs/heads/master.zip
mv zsh-autosuggestions-master .oh-my-zsh/plugins/zsh-autosuggestions

wget --no-check-certificate  https://github.com/romkatv/powerlevel10k/archive/refs/heads/master.zip
mv powerlevel10k .oh-my-zsh/custom/themes/powerlevel10k

```


source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh


# 磁盘

```bash
mkdir -p /media/cdrom
mount -o loop /data/debian-12.4.0-amd64-DVD-1.iso /media/cdrom

mkfs.ext4 -F -L "rootfs" /dev/sda1

#查看磁盘UUID
blkid /dev/sda1

```



# 安装

```
grub-install --removable --recheck --efi-directory=/boot/efi

```



# USB

USB2 port 3, 4, 6


# GPU

nvidia-smi