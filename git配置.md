~~~
HEAD是一个指针
tail -n 3 good.txt													显示最后三行
~~~
### 建文件
mkdir mm															新建文件夹mm
cd mm																	打开文件夹mm
git init																	初始化仓库

### 设置签名
																				项目级别
git config user.name 用户名		
git config user.email 邮箱
																				系统用户级别
git config --global user.name
git config user.email
信息保存位置			./git/config

### 三个区
* 工作区
* 暂存区
* 本地库

### 添加、提交、修改
git add x.txt														 添加操作
git commit -m "提交说明"							提交操作
git status															   状态查看

### 历史记录
git log																	查看完整的历史记录从近到远
~~~
多屏显示：
* 空格向下翻页
* b 向上翻页
* q 退出
~~~
git log --pretty=oneline							查看历史记录只显示一行
git log --oneline											查看历史记录只显示前7位索引值
git reflog															查看历史记录可以看到距离当前版本几步
~~~
HEAD 中的数字是到当前版本的步数
~~~

回退某一个版本
~~~
git reset --hard [局部索引值]
git reset --hard 03a3cd1					   回退到 03a3cd1版本
git reset --hard HEAD^							回退上一个版本
git reset --hard HEAD~n						  回退上n个版本
~~~
**重置三个参数**
* soft参数
	* 仅仅在本地库移动HEAD指针
* mixed参数
	* 在本地库移动HEAD指针
	* 重置暂存区
* hard参数
	* 在本地库移动HEAD指针
	* 重置暂存区
	* 重置工作区

### 删除文件找回
* 前提：删除前，文件存在时状态提交到本地库
* 操作：git reset --hard [指针位置]
	* 删除操作到本地库：指针指向历史记录
	* 删除操作没提交到本地库：指针只想HEAD

### 比较文件差异
~~~
git diff [文件名]
			工作区的文件和暂存区进行比较
git diff [本地库版本历史记录] [文件名]
			工作区的文件和本地库历史记录比较
不带文件名比较多个文件
~~~
### 分支
创建分支
~~~
git branch [分支名]
~~~
查看分支
~~~
git branch -v
~~~
切换分支
~~~
git checkout [分支名]
~~~
合并分支
~~~
切换接受修改的分支上（被合并，增加内容）
git checkout [分支名]
执行merge
git merge [分支名]
~~~

### 分支冲突
~~~
编辑文件，删除特殊符号
git add [文件名]
git commit -m "日志信息"
		此时commit一定不可以带具体文件名
~~~

### 克隆
~~~
git clone [远程地址]
完整的把远程库下载到本地
创建origin远程地址别名
初始化本地库
~~~
### 远程库修改的拉取
~~~
pull=fetch+merge
git fetch origin [远程库地址别名] [远程分支名]
git merge [远程库地址别名/远程分支名]
~~~