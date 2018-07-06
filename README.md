# gitLearning
github 上传以及git push代码遇到:refusing to merge unrelated histories或者non-fast-forward

下载安装GIT,一直下一步就OK 了
在你的工程文件下（例如：C：/WORK/test，WORK 是你的仓库，test就是你的工程文件，要上传的东西）右击 有git bash Here 就可以打开git 的命令窗口
输入以下命令 
$ git config --global user.name "xiancai" 
$ git config --global user.email "xiancai@163.com" 
输入你的用户名和邮箱 
先检查有没有密钥 输入 
cd ~/.ssh 
若返回有id_rsa id_rsa.pub则密钥已经产生进入C:\User\admin(你的电脑用户名)\.ssh id_rsa.pub 是公钥 另一个是私钥 公钥要用。如果没有则输入以下命令： 
`$ ssh-keygen -t rsa -C “xiancai@163.com” 
然后打开id_rsa.pub 用记事本打开它复制它
申请github账号 点击右上角的 头像，下拉列表里面有settings 点击，左侧有SSH 点击 右上角有NewSSHKye 点击 title 随便写便于分辨就好 复制公钥 OK
cd test 进入test文件夹 （这个就是你要上传的文件）执行以下命令 
git init 
git add . 
git commit -m "提交文件"（提交文件只是注释） 
git remote add origin https://github.com/xaincai/dailyfresh.git 
(xaincai 是我的github 用户名 dailyfresh 是我的新建的一个工程的 名字) 
******************** 
如果有人git push代码遇到:fatal: refusing to merge unrelated histories 则直接运行以下步骤： 
（原因在于你github上有README 而本地没有，导致远程分支和本地分支不一样） 
git pull --rebase origin master（这样会在本地仓库新建一个readme文件这样就可以了） 
git push -u origin master 
