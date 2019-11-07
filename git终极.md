## <font color="red">Git起步</font>
### 两种控制系统
#### 集中化的版本控制系统
好处：每个人都可以一定程度看到项目其他人做什么
坏处：有丢失数据的风险，最坏的就是丢失整个项目的所有历史记录
#### 分布式版本控制系统
好处：有服务器发生故障，事后可以用任何一个镜像出来的本地仓库恢复

### Git简史
对Git制定的目标
* 速度
* 简单的设计
* 对非线性开发模式的强力支持（允许上千个并行开发的分支）
* 完全分布式
* 有能力高效管理类似LInux内和一样的超大规模项目（速度和数据量）

### Git简单基础
#### 直接记录快照，而非差异比较
#### 近乎所有操作都是本地执行
#### 时刻保持数据完整性
> GIt使用SHA-1 算法计算数据的校验和

#### 多数操作仅添加数据
#### 文件的三种状态
1.已提交（committed）
2.已修改（modified）
3.已暂存（staged）
#### 文件的三个工作区域
* Git工作目录
* 暂存区域
* 本地仓库

#### Git工作流程
1.工作目录中修改某些文件
2.修改后的文件进行快照，保存暂存区域
3.提交更新，将保存在暂存区的文件快照永久转储到Git目录中


#### Linux安装
> apt-get install git

#### GIt配置
1.用户信息
> git config --global user.name "gaozzb"
> git config --global user.email "2711600326@qq.com"

2.  查看配置信息
> git config --list

## <font color="red">Git基础</font>
### 取得项目仓库
#### 初始化仓库
> git init
> git add 文件
> git commit -m "提交说明"

#### 从现有仓库克隆
> git clone ssh链接地址

### 记录每次更新到库
#### 检查当前文件状态
> git status

#### 跟踪新文件
> git add 文件
> git status

#### 暂存已修改文件
> vim 文件（修改一次）
> git status
> git add 文件
> vim 文件
> git status
> git add 文件

#### 忽略文件
创建一个.gitignore文件
文件格式规范：

* 所有空行或者注释符号`#`开头的行都会被Git忽略
* 匹配模式最后跟反斜杠（`/`）说明要忽略的目录
* 要忽略指定模式以外的目录或文件，可以在模式前加上惊叹号（`!`）取反

#### 查看已暂存和未暂存的更新
> git diff		查看尚未暂存的文件更新了哪些部分
> git diff --staged		查看已经暂存的文件和上次提交时的快照之间差异
> git diff --cached

#### 跳过使用暂存区
> git commit -a -m "提交说明"			可以跳过git add

#### 移除文件
> git rm --cached 文件
> git rm \*~		递归删除当前目录以及子目录所有~结尾的文件

#### 移动文件
> git mv file_old file_new		改名字

#### 查看提交历史
> git clone git@github.com:gaozbb/nmnm.git		克隆库
> git log		查看历史
> git log -p -2		查看最近两次更新
> git log --stat	查看增改行数统计
> git log --pretty=format:"%h - %an, %ar : %s"		查看显示记录的格式

#### 取消文件
> git reset HEAD x				取消暂存的x文件
> git checkout -- x				取消对文件的修改

#### 远程仓库的使用
> git clone git@github.com:gaozbb/git-Dev.git			克隆远程库
> git remote -v					查看远程库

#### 添加远程库
> git remote add origin git@github.com:gaozbb/git-Dev.git		添加一个远程库
> git fetch origin		

#### 查看远程仓库信息
> git remote show origin

#### 删除远程仓库和重命名
> git remote rename pb paul					把远程仓库的pb改成paul
> git remote rm paul								  删除远程仓库paul

#### 打标签
> git tag															列出现有标签
> git tag -l "v1.4.2.*"									  贴上标签

#### 含附注的标签
> git tag -a v1.4 -m "my version 1.4			创建一个含附注类型的标签
> git show v1.4						查看对应标签的版本信息