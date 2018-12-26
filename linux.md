## Mac

* open new terminal/web `command + T`
* switching between terminals `control + Tab`
* switching between applications `command + Tab`
* `find ./ -name "*.java" | xargs grep -n "keyword"`

## item2
```
⌘ + t: 新开标签页

⌘ + 方向键 按方向切换标签页。

⌘ + d: 垂直分屏，

⌘ + shift + d: 水平分屏。

⌘ + ]和⌘ + [在最近使用的分屏直接切换.

⌘ + opt + 方向键切换到指定位置的分屏。

⌘ + 数字: 切换标签页。 

shift + ⌘ + s: 保存当前窗口快照。

⌘ + opt + b: 快照回放。很有意思的功能，你可以对你的操作根据时间轴进行回放。可以拖动下方的时间轴，也可以按左右方向键
```

## Docker

* daocloud 下载源 

  http://get.daocloud.io/#install-docker-for-mac-windows

* get started

  https://docs.docker.com/get-started/#prerequisites
  
* run hello world

  ```
  huizhu@Master:~$ sudo docker run hello-world
  docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?.
  ```
  ```
  huizhu@Master:~$ sudo service docker status
  huizhu@Master:~$ docker stop/waiting
  huizhu@Master:~$ sudo service docker start
  docker start/running, process 26898
  huizhu@Master:~$ sudo docker run hello-world
  ```
  
* jiang

```
sudo docker run -i -t -v /home/huizhu/bitbucket/:/root/app -w=/root/app pyenv /bin/bash
env PYTHONPATH=. python foundation/utils/rdkit_utils_test.py
```
  
## Linux

* shadowsocks server

  ```
  sudo ssserver -k 123456 -m aes-256-ctr -p 554
  ```
  sslocal 
  
  `sslocal -s ip -k password -m aes-256-ctr -p 554`
  
  
* 命令行下获取当前路径 `pwd`

* jupyter notebook ip port `jupyter notebook --ip=172.11.30.49 --port=8989`


* `sudo useradd huizhu` (无需创建密码) `sudo deluser huizhu` 删除创建的用户


* `sudo adduser huizhu` (需要创建密码)

* 修改用户密码 `passwd`


* 压缩／解压缩

* Linux 解压缩 

  http://jingyan.baidu.com/article/6d704a13f9981a28da51ca70.html
  
  ```
  rar x Filename.rar (解压缩)
  ```
  ```
  tar zcvf Filename.tar.gz DirName (压缩)
  tar zxvf Filename.tar.gz (解压缩)
  ```
  ```
  tar -cf all.tar *.jpg (打包)
  tar -xf all.tar (解包)
  tar -czf all.tar.gz *.jpg (打包+压缩)
  tar -xzf all.tar.gz (解包＋解压缩)
  ```
  ```
  tar -jxvf Filename.tar.bz2
  ```
  ```
  zip -r Filename.zip DirName1, abc.txt (压缩)
  unzip Filename.zip (解压缩)
  gzip -d Filename.gz
  ```
  
* xrandr 查看屏幕显示分辨率
* lspci　查看显卡参数信息
* Linux 垃圾回收箱位置

  `cd ~/.local/share/Trash/files/`

* Linux统计文件大小 
  ```
  du -h --max-depth=1  #统计当前文件夹内所有子文件/子文件夹的大小 
  du -h --max-depth=1 dir_name/  #统计dir_name内所有文件的大小 
  ls -l | grep "^-" | wc -l  # 查看统计当前目录下文件的个数 
  ls -lR| grep "^-" | wc -l  #查看统计当前目录下文件的个数，包括子目录里的。 
  ls -lR| grep "^d" | wc -l  #查看当前目录下文件夹(目录)的个数，包括子目录里的。 
  ```
  http://www.cnblogs.com/kysnail/archive/2012/03/25/2417221.html #查看文件系统类型 
  
* 替换文件名称
  
  `rename "s/AA/aa/" *`  #把当前文件夹下所有文件名中的AA替换成aa, 不要忘记 *
  

* 查找字符串
  ```
  grep -rn "hello,world!" * #查看当前文件夹下哪些文件里含有字符串"hello,world!"
  find ~/git_test/ -name test.py  # 在~/git_test文件夹下查找名字为test.py的文件
  ```
* 查看硬盘使用情况
  '''
  df -hl
  '''
 
* 查看当前文件夹占用空间大小
  '''
  du -sh
  '''


## bash

* shell 变量

  http://www.cnblogs.com/barrychiao/archive/2012/10/22/2733210.html

* bash 不同版本
  ```
  huizhu@huizhu:~$ cat /etc/shells
  # /etc/shells: valid login shells
  /bin/sh
  /bin/dash
  /bin/bash
  /bin/rbash
  /usr/bin/tmux       
  ```


## linux operation system

* Linux 版本号
  ```
  cat /etc/lsb-release
  sudo lsb_release -a
  cat  /etc/issue
  ```
  
* Linux i86
  ```
  huizhu@huizhu:~$ echo "`uname -s` `uname -m`"
  Linux i686 版本号
  huizhu@huizhu:~$ echo "$USER"
  huizhu
  huizhu@huizhu:~$ 
  ```
* ubuntu 16.04 调节屏幕亮度

  http://www.cnblogs.com/zero-zf/p/5954821.html

    1. 修改grub
    ```  
    sudo vim /etc/default/grub 把文件中的 GRUB_CMDLINE_LINUX="" 修改为`GRUB_CMDLINE_LINUX="acpi_backlight=vendor"
    ```
 
  2. 更新 `grub`
    ```
    sudo update-grub
    ```
    
  3. 修改亮度数值
    `echo 50 > /sys/class/backlight/intel_backlight/brightness` 
    
    将上面这句代码添加到文件 `/etc/rc.local` 中，这样每次开机屏幕亮度都是 `50` (该值可以是(0 - 976)之间的任一值)
    


## python

* 将异常信息拦截 `python test.py 2> error.txt`

* format

  https://pyformat.info/
  

### joblib vs numpy vs cPickle

  我们使用矩阵 **x_dense** 和 **x_sparse**　对`joblib`, `numpy` 和 `cPickle`存储/读取性能进行测试, 其中

  `x_dense = np.random.binomial(2, 0.01, size=(1000, 1000))` 

  ```
  indices = np.where(x_dense != 0)
  data = x_dense[indices]
  x_sparse = csr_matrix((data, indices), shape=x_dense.shape)
  ```

  测试存储的文件字节大小以及读取文件时间分别为:

  |        |dense |       |sparse|       |
  |--------|------|----------|------|----------|
  |        | bytes| load time|bytes | load time|
  |joblib  |100k  | 7.21ms   |40k   | 0.495ms  |
  |numpy   |7.7M  | 1.18ms   |240k  | 0.181ms  |
  |cPickle  |31M| 1.02s    |928k  | 30.3ms  |
  
  因此可以看出, joblib 和 numpy 分别在文件大小和读取时间上各自有优势，而 cPickle 在两方面都远远落后。
  三种存储方法为
  
  ```
  joblib.dump(data, filename)
  np.save(open(filename, 'w'), data)
  cPickle.dump(data, open(filename, 'w'))
  ```
  
  
pip 源
  
  https://mirrors.tuna.tsinghua.edu.cn/help/pypi/

临时使用
  ```
  pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
  ```
设置默认
  ```
  修改 ~/.config/pip/pip.conf (Linux), %APPDATA%\pip\pip.ini (Windows 10) 或 $HOME/Library/Application Support/pip/pip.conf      (macOS) (没有就创建一个)， 修改 index-url 至 tuna，例如

  [global]
  index-url = https://pypi.tuna.tsinghua.edu.cn/simple
  ```
