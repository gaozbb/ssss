# Linux 兄弟连


## 文件处理命令

### 目录处理命令
~~~
ls								  查看文件
ls -a							    查看所有文件
ls -l								 查看文件获取详细信息
ls -lh							查看文件带大小有单位
ls -ld							查看目录信息
ls -i								  查询任何一个文件i节点
~~~

### 文件处理命令

```
touch						创建文件
cat								查询文件内容
tac								显示文件内容（倒着显示）
more							分页显示文件内容
less							   分页显示文件内容（可以向上翻页）
head -n					  显示文件前几行
tail -n						  显示文件末尾几行
tail -f							动态显示文件末尾内容
```

**软链接和硬链接**
~~~
ln -s								创建软连接
软链接特征，类似Windows快捷方式
ln								  创建硬链接
硬链接特征，拷贝cp -p + 同步更新
~~~

### 权限管理命令
~~~
chmod +-=修改权限
r			4
w		   2
x			 1
chmod +R 递归修改

chown
~~~
> r			读权限			r:ls
> w		   写权限			w:/touch/mkdir/rmdir/rm
> x			执行权限		x:cd

### 文件搜索命令
* find
~~~
find /路径 -name init					搜索
find /路径 -size +204800			查找大于100mb的文件
find /home -user xxx				查找所有者为xxx的文件
find /路径 -cmin -5					查找五分钟内被修改过的属性文件和目录
find /路径	-size +163840 -a -size -204800			查找大于80MB小于100MB的文件
find /路径	-name	init*	-a	-type	d					查找文件下所有的目录
find /路径 -user xx	-ok	rm {} \;				删除所有用户名xx的文件并询问是否
find .	-inum i节点	-exec rm	{}	\;			删除当前目录下的i节点文件

-a		两个条件同时被满足
-o		两个条件满足任意一个
-amin	访问时间		access
-cmin	文件属性		change
-mmin	文件内容		modify

f文件				d目录			l软链接文件

1数据块=512字节		0.5k
1MB=1024KB
~~~
* locate
~~~
updatedb		更新文件资料库
locate -i			不区分大小写查找
~~~

### 帮助命令
~~~
man 				查看命令或配置文件帮助信息
whatis				看命令简短信息
apropos				获得配置文件相关信息
命令 --help		获得命令主要选项信息
man date		查看日期参数
help					查看shell内置命令
~~~

### 用户管理命令
~~~
useradd
passwd

who查看登录用户信息
w		查看当前登录用户详细信息
~~~

### 压缩解压命令
~~~
.gz
gzip		压缩
gunzip		解压缩

tar		打包
tar -zcf	文件名.tar 文件名			打包目录
tar -zxvf	文件名.tar 文件名			解包

zip xx.zip xx							压缩.zip
zip -r xx.zip xx						压缩目录

-x			解包
-v			显示详细信息
-f			指定解压文件
-z			解压缩
~~~