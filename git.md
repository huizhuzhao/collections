
## errors

* `fatal: The remote end hung up unexpectedly`
  
  `git config http.postBuffer 524288000`

* `credental.helper`
  
  https://help.github.com/articles/caching-your-github-password-in-git/
  
## commands

* common
  ```
  git remote show origin #显示远程所有分支信息
  git tag -l #显示所有tag
  ```
  ```
  git fetch <name>
  git merge <name>/master  # 达到 `git pull`的效果
  ```
  ```
  git remote -v #简单的展示所有 <name> <url> 的信息
  git remote show <name> #详细展示远程仓库 <name>, 包括本地分支与远程分支间的追踪关系
  git branch -r #简单展示所有remote分支
  git branch -v #查看所有分支最近一次的提交信息
  git branch -vv #查看本地分支与远程分支之间的追踪关系，以及本地分支是否超前或者落后(ahead/behind)于远程分支
  ```
  ```
  git branch -d <branch_name> #删除分支
  git push <name> --delete <branch_name> #删除远程分支 <name>/<branch_name>
  ```

* 在文件夹中添加remote url
  ```
  mkdir simplegit
  cd simplegit
  git init 　　#初始化git文件夹
  git remote add <name> <url> #设置远程仓库<url>在本地的名字为<name>，通常情况下<name>设置为origin
  git fetch <name>
  ```

* 从远程下载内容，checkout, pull, merge
 
  ```
  git checkout -b master #创建本地分支master
  git merge <name>/master #将远程分支<name>/master内容合并到本地当前分支
  ```
  ```
  git checkout -b master <name>/master #创建新的本地分支master，该本地分支内容将与远程分支<name>/master建立**跟踪**关系(tracking)
  ```
  上面两种方法的区别：在使用`git pull`时第一种方法会报错，因为该方法并没有建立本地分支(maser)与远程分支(<name>/master)之间的　**tracking**　关系（可以通过`git branch -u <name>/master master`建立）
  但是可以使用 

  
* 从本地上传内容到远程分支
  ```
  git checkout -b dev #创建本地dev分支
  git push <name> dev:<remote_dev> #将本地dev分支上传到远程分支<remote_dev>
  git branch -u <name>/<remote_dev> dev #建立本地分支 dev 和远程分支 <name>/<remote_dev> 之间的追踪关系
  ```

* git clone后将对应的远程分支下载到本地步骤：
  ```
  git clone https://xxxxxxx
  git remote set-branches --add origin dev
  git fetch
  git checkout -b dev origin/dev
  ```
  
* git tag

  ```
  git tags # 显示所有标签
  git checkout tags/<tag_name> #查看 <tag_name> 的内容
  git checkout tags/<tag_name> -b <branch_name> # 基于 <tag_name> 新建分支
  ```

## webs

* https://git-scm.com/doc

* git log

  https://git-scm.com/book/zh/v1/Git-%E5%9F%BA%E7%A1%80-%E6%9F%A5%E7%9C%8B%E6%8F%90%E4%BA%A4%E5%8E%86%E5%8F%B2

* OpenGithub 新项目快报

  http://www.open-open.com/github/view/github2016-10-24.html

* git常用命令
  
  http://blog.csdn.net/dengsilinming/article/details/8000573
  
  http://rogerdudler.github.io/git-guide/index.zh.html
