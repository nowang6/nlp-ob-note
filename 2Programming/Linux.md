vast.ai

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

#查询安装的包
dpkg-query -l

#/etc/apt/sources.list
deb [trusted=yes] file:///mnt/debian-cd bookworm main contrib


whereis goldendict

apt show goldendict

apt list --installed

用于搜索包
apt-cache

```

## shell 和插件

```bash
apt install zsh -y
#将 zsh 设置为默认 Shell
chsh -s /bin/zsh

# on my sh
mv ohmyzsh-master ~/.oh-my-zsh
https://gist.github.com/hewerthomn/65bb351bf950470f6c9e6aba8c0c04f1
./install-oh-my-zsh.sh

# auto-suggestion
https://github.com/zsh-users/zsh-autosuggestions/archive/refs/heads/master.zip
mv zsh-autosuggestions-master .oh-my-zsh/plugins/zsh-autosuggestions

# powerlevel10k
https://github.com/romkatv/powerlevel10k/archive/refs/heads/master.zip
mv powerlevel10k .oh-my-zsh/custom/themes/powerlevel10k

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`
export TERM=xterm-256color
```


# 磁盘

```bash
mkdir -p /media/cdrom
mount -o loop /data/debian-12.4.0-amd64-DVD-1.iso /media/cdrom

mkfs.ext4 -F -L "rootfs" /dev/sdb1
mkfs.exfat -n xq_256 /dev/sdb1


#查看磁盘UUID
blkid /dev/sda1

#/etc/fstab
/data/debian-12.4.0-amd64-DVD-1.iso /mnt/debian-cd/ udf,iso9660 loop 0 0

/etc/fstab
/data/debian-12.4.0-amd64-DVD-1.iso /media/cdrom auto loop 0 0
mount -a

```




## 系统

```bash
#关闭睡眠
 systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```


# USB

USB2 port 3, 4, 6


# GPU

```bash
pip install torch
#i

pip install flash_attn

pip install bitsandbytes==0.39.0
#python -m bitsandbytes


pip install transformers 
#from transformers import AutoModelForCausalLM, LlamaForCausalLM, LlamaTokenizer
pip install accelerate peft loguru

```

[install link](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Debian&target_version=12&target_type=deb_network)

```bash
vim /etc/modprobe.d/blacklist.conf
blacklist nouveau

update-initramfs -u

#卸载
apt-get remove --purge '^nvidia-.*'
apt-get remove --purge '^libnvidia-.*'
apt-get remove --purge '^cuda-.*'

apt search nvidia-driver

#安装依赖
apt-get install build-essential
apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev vim curl

#安装
dpkg -i cuda-keyring_1.1-1_all.deb
add-apt-repository contribsudo apt-get update
apt-get -y install cuda-toolkit-12-3
apt-get install -y cuda-drivers

nvidia-smi
nvidia-smi topo --matrix
```


```bash
# uninstall
apt-get --purge remove "*cuda*" "*cublas*" "*cufft*" "*cufile*" "*curand*" \
 "*cusolver*" "*cusparse*" "*gds-tools*" "*npp*" "*nvjpeg*" "nsight*" "*nvvm*"
apt-get --purge remove "*nvidia*" "libxnvctrl*"
apt-get autoremove

```
# Nrok

```
tar -xvzf ngrok-v3-stable-linux-amd64.tgz -C /usr/local/bin
nohup ngrok http 8080 --log=stdout > ngrok.log &
```


# Tmux 多窗口工具



# docker

```bash
apt-get update
apt-get install ca-certificates curl
install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
apt-get update


apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

```
