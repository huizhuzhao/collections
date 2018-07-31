## pip

* pip 源
  ```
  https://mirrors.tuna.tsinghua.edu.cn/help/pypi/
  ```
  
* 临时使用
  ```
  pip install -i https://pypi.tuna.tsinghua.edu.cn/simple tensorflow-gpu==1.3
  ```
  
* 设置默认

  ```
  修改 ~/.config/pip/pip.conf (Linux), %APPDATA%\pip\pip.ini (Windows 10) 或 $HOME/Library/Application Support/pip/pip.conf (macOS) (没有就创建一个)， 修改 index-url 至 tuna，例如
  
  [global]
  index-url = https://pypi.tuna.tsinghua.edu.cn/simple
  ```

## conda

设置 conda tuna 源

  ```
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  conda config --set show_channel_urls yes
  ```
