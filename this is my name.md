# Typora简单语法
[toc]
## 块元素
一级标题		#一级标题
二级标题		##二级标题
三级标题		###三级标题

## 块引用
> this is a blockquote with two
> this is second pragraph.Vestibulum enim wisi, viverra nec
> 用>引用引文部分

## 清单
输入* list将创建一个无序列表
* list
* list

在无序列表行头加入tab键（空三个格），即可进入二级内嵌列表
* list
* list
	* list
	* list

输入1.（英文的点）将创建一个有序列表
1.list
2.list

在游戏列表行头加入tab键（空三个格），即可进入二级内嵌有序列表
1.list
2.list
	1.list
	2.list

## 任务列表
- [ ] 男
- [ ] 女
- [x] 保密

## 代码块
输入```按下return，在```之后添加可选语言标识符
```html
<table border="1">
<tr>
<td>23</td>
<td>123</td>
</tr>
</table>
```

## 数学块
添加数学表达式，输入$$按下Return，由$$结尾包裹
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$

## 桌子
输入| First | Second | Three |并按下return键，创建一个包含两列的表。第二行输入| - | - | - |
| First | Second | Three |
| - | - | - |
| First | Second | Three |

可以在表中包括内联Markdown，例如链接，粗体，斜体或删除线。
通过：在标题行中包含冒号（），可以将该列中的文本定义为左对齐，右对齐或居中对齐
| First | Second | Three |
| :- | :--: | -: |
| First | Second | Three |

## 脚注
在需要添加的文字后方加上[^]里面填写内容
农夫山泉有点[^咸]

## 水平尺
在空白行上输入***或---，然后return绘制一条水平线

***

## YAML首要事项
tupora支持yaml front matter。---在文章顶部输入，然后return引入一个元数据块，或者可以吃typora顶部菜单插入元数据块
## 目录
输入[toc]并return按键，将创建"目录"部分，toc会从文档中提取所有标题，并且添加文档时，自动更新内容。
## 链接
Markdown支持两种样式链接，内联和引用。
在这两种样式中，链接的文本均有[方括号]分隔。
创建内联链接，在链接文本中的右方括号后立即使用一组常规括号。在括号内，将URL指向链接要指向的位置，以及链接的可选标题，并用引号引起来。
This is [an example](http://example.com/ "Title") inline link.
[Google][]

[Google]:http://google.com/

## 网址
Typora允许插入URL作为链接，并用方括号括起来。
<27116@qq.com>
## 图片
图像的语法与链接相似，但是!在链接开始之前需要额外的字符
<img src="C:\Users\Cnm\Pictures\桌面壁纸\1.jpg" alt="Alit text" style="zoom: 25%;" />
![](图片url)

## 重点
Markdown将星号（*）和下划线（_）视作为重点。用*或_包裹的文本将带有<HTML>文本<em>斜体效果

*single asterisks*
_single asterisks_

## 删除线
用~~~~包裹文本进行删除线操作

~~删除~~
## 下划线
用html语法<u></u>进行下划线操作

<u>下划线</u>

## 表情符号
使用语法输入表情符号​：:smile。
用户可以通过ESC按键触发表情符号的自动完成建议，也可以在首选项面板上启用它后自动触发。此外，还可以通过转到菜单栏中国的Edit->直接输入UTF-8表情符号字符Emoji & Symbols。

:blonde_woman:
