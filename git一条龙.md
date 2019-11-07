#### 配置用户名邮箱
~~~
git config --global user.name "gaozzb"
git config --global user.email "2711600326@qq.com"
~~~

#### 初始化仓库
~~~
git init
~~~

#### 添加本地仓库
~~~
vim readme.txt
git add readme.txt
git status
git commit -m "提交说明"
git status
~~~

#### 查看修改
~~~
git diff readme.txt
~~~

#### 查看历史记录
~~~
git log			查看从最近到最远的记录
git log --pretty=oneline			查看记录版本号
git log --graph --pretty=oneline --abbrev-commit			查看分支历史
git reflog		记录每一次命令
git diff HEAD -- readme.txt				查看工作区和版本库的最新版本区别
~~~

#### 回退版本
~~~
git reset --hard HEAD^				回退到上一个版本
git reset --hard 4位数的版本号		退回某一版本
~~~

#### 三个区
* 工作区
* 暂存区
* 版本库
	* 隐藏一个.git目录，这是Git版本库

#### 撤销修改
~~~
git checkout -- readme.txt			丢弃工作区的修改
git reset HEAD readme.txt			暂存区的修改撤掉
~~~

#### 创建SSH key
~~~
ssh-kegen -t rsa -C "2711600326@qq.com"
cd ../.ssh
cat id_rsa.pub
~~~

#### 本地仓库建立与远程仓库连接
~~~
gti remote add origin git@github.com:gaozbb/new.git		关联远程仓库
git push -u origin master		本地库推送到远程仓库（第一次要加-u）
git push origin master			本地提交远程
git clone git@github.com:gaozbb/kill.git		克隆库
~~~

#### 分支
~~~
git checkout -b dev				创建并切换分支
git branch dev						 创建分支
git checkout dev				  切换分支
git branch								 查看所有分支
git branch -d dev				  删除分支
git merge dev						合并某分支到当前分支
~~~

#### 解决冲突
~~~
git checkout -b fea				创建fea分支
vim readme.txt					   修改
gti add readme.txt				加入暂存区
git commit -m "AND"			提交版本库
git checkout master			  切换分支
vim readme.txt					   修改
git add readme.txt				加入暂存区
git commit -m "xim"			 提交版本库
git merge fea						  合并分支
cat readme.txt						查看文件
vim readme.txt					   修改
git add readme.txt				加入暂存区
git commit -m "tijiao"		 提交版本库
~~~

#### 分支管理
~~~
git checkout -b fea				创建fea分支
vim readme.txt					   修改
gti add readme.txt				加入暂存区
git commit -m "AND"			提交版本库
git checkout master			  切换分支
git merge --no-ff -m "merge" dev			合并分支并且提交
~~~

#### Bug分支
~~~
git stash				保存工作目录和索引
git branch -D 文件				丢弃一个没有被合并过的分支
~~~

#### 多人协作
~~~
git remote				查看远程库信息
git remote -v			查看更详细的信息
git push origin master		推送该分支到远程
git push origin dev				推送dev分支
~~~

分支需要推送
* `master`分支是主分支，因此要时刻与远程同步
* `dev`分支是开发分支，团队成员需要在上面工作，所以需要与远程同步
* `bug`分支只用于本地修复bug，没必要推送到远程，除非老板要看
* `feature`分支是否推到远程，取决于是否和别的小伙伴合作开发

#### 标签
* git tag 标签名				 创建标签
* git tag -a 标签名 -m "提交说明"
* git tag								查看所有标签
* git tag -d 标签名			删除标签
* git push origin v1.0		推送某个标签到远程
* git push origin --tags		一次性推送还没推送到远程的本地标签

删除远程标签
* git tag -d v0.9				删除本地标签
* git push origin :refs/tags/v0.9		删除远程

#### 配置别名
git config --global alias.st status			以后status被st表示