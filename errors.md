
### mount

```
mkdir /dir_name fdisk -l # 确定移动硬盘的名称 /dev/xxxx 

sudo mount /dev/xxx /dir_name
```

### nvidia X server

```
This worked for me

sudo rm /tmp/.X*-lock
sudo apt-get purge nvidia-*
sudo reboot
sudo service lightdm stop
press alt+F1 
sudo rmmod nvidia
sudo sh cuda_8.0.61_375.26_linux.run 
sudo service lightdm start

and reboot
```

###  ImportError: libcudart.so.8.0: cannot open shared object file: No such file or directory

```
sudo ldconfig /usr/local/cuda/lib64
```

### cuda install
```
PATH includes /usr/local/cuda-8.0/bin
LD_LIBRARY_PATH includes /usr/local/cuda-8.0/lib64, or, add /usr/local/cuda-8.0/lib64 to /etc/ld.so.conf and run ldconfig as root

```

### tensorflow libcublas.so.8.0

https://devtalk.nvidia.com/default/topic/1026198/cuda-9-0-importerror-libcublas-so-8-0/

### 豆瓣源

```
[global] 
index-url = http://pypi.douban.com/simple/ 
trusted-host = pypi.douban.com 
```
添加到 ~/.pip/pip.config 中




### certificate error

```
[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed (_ssl.c:645)

sudo update-ca-certificates
```


### ubuntu系统开机后进入grub页面
```
error:file "/boot/grub/i386-pc/normal.mod" not found
Entering rescue mode...
grub rescue>
```
该页面仅支持`set,ls,insmod,root,prefix`这些命令，　解决的办法有二，

 1. 去下面网站下载`boot-repair` https://help.ubuntu.com/community/Boot-Repair 
(按照官方介绍即可,我使用Rufus制作u盘启动器)
 2. http://askubuntu.com/questions/192621/grub-rescue-prompt-repair-grub (没有试成功)

