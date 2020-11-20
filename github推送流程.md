## 创建文件夹，并进入

git init   // 初始化版本库
git add .   // 添加文件到版本库（只是添加到缓存区），.代表添加文件夹下所有文件 
git commit -m "first commit" // 把添加的文件提交到版本库，并填写提交备注

## 到目前为止，我们完成了代码库的初始化，但代码是在本地，还没有提交到远程服务器，所以关键的来了，要提交到就远程代码服务器，进行以下两步

git remote add origin 你的远程库地址  // 把本地库与远程库关联
git push -u origin master    // 第一次推送时
git push origin master  // 第一次推送后，直接使用该命令即可推送修改

## 把本地库的内容推送到远程。使用 git push命令，实际上是把当前分支master推送到远程。执行此命令后会要求输入用户名、密码，验证通过后即开始上传。
说明：用户名密码需要通过命令 ssh-keygen -t rsa -C “xxxxxx@qq.com”进行创建，并且要把得到的秘钥（公钥）文件放到git服务器上，这样才有权限进行代码推送

到此就成功的把本地的代码放到了远程服务器上，这样就能让项目组成员进行写作开发了。

============================================
git拉取远程分支到本地

新建一个空文件，文件名可以自定义
初始化：git init
与远程分支建立连接：git remote add origin git@gitLab.com:xxxxx.git （打开gitlab仓库，在clone下复制的地址）
把分支拉取到本地：git fetch origin dev (dev 为远程仓库的分支名)
在本地创建分支dev并切换到该分支：git checkout -b dev(本地分支名) origin/dev(远程分支名)
把远程代码拉取到本地：git pull origin dev(dev为远程的分支名)
提交代码到远程

查看git状态：

git status
提交代码到本地仓库：

git add .（提交全部）
git add 文件路径 （提交指定文件）
git commit -m "提交描述"
提交代码到远程git：

git push origin dev


============================================
============================================

#### 补充

1.不用每次都输入密码

git不用每次输入用户名和密码（第一次需要正常输入用户名密码）

git config --global credential.helper store
git pull /git push (这里需要输入用户名和密码，以后就不用啦)

