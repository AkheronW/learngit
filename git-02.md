# Git-2
### 三个主要部分
* 工作区(Working directory)
* 暂存区(Staging area)
* 仓库区(.git directory)
***工作区*** 存放项目所有文件，每个文件都有文件状态(` untracked `,` unmodified `,` modified `,` staged `)；与.git目录在同一个目录下
***暂存区*** 也被称为` stage `或者` index `，暂存区是一个假象的层次，当运行 ` git commit `命令后，仓库区中的内容将于仓库区的内容合并
***仓库区*** 可以看作git仓库的数据库（存放了每次提交后的项目快照，有利于回滚）以及其它数据

		 Working                 Staging             .git directory 
		Directory                 area                (Repository)
		    |                       |                     |
		    |      git checkout     |                     |
		    | <========================================== |
		    |                       |                     |
		    |     git add           |                     |
		    | =====================>|                     |
		    |                       |                     |
		    |                       |   git commit        |
		    |                       | ===================>|
		    |                       |                     |
		    |                       |                     |
		    |                       |                     |

> ` git checkout ` 从仓库区的某个特定分支中获取最新项目快照，并将从快照恢复的项目数据放入工作区，此时工作区文件状态都为` unmodified `
> ` git add ` 工作区中文件执行此命令放入了暂存区
> ` git commit ` 执行此命令可将处于暂存区的文件与上一次快照合并生成新的快照，此时所有文件状态转换为` unmodified `

#### 上述三个主要部分还可以由以下两个图表示

![ ](./git/three-parts-1.png  "three-parts1")

以及来自廖雪峰老师网站的图

![ ](./git/three-parts-2.jpg  "three-parts2")

#### git仓库中的文件状态

		          |----------------------Tracked----------------------------| 
		          |                                                         |
	Untracked             Unmodified             Modified                Staged 
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |
	    |                      |                     |                     |

> 可用 ` git status `命令查看文件状态

### git clone
```
	git clone https://github.com/fffaraz/awesome-cpp.git #克隆远程仓库，这里通过https，也可通过其它协议；克隆成功后项目文件会在当前目录下名为awesome-cpp的目录里
	#如需自己指定文件名
	git clone https://github.com/fffaraz/awesome-cpp.git awesome
```
###  git add
> ` git add `命令有较多参数，以下列出` Git 2.x `版本的一些使用方法

| 参数 | 新创建 | 已删除 | 已修改 |  |
| :----- | :-----: | :-----: | :-----: | :-----: |
| git add -A | &radic; | &radic; | &radic; | 将所有工作区文件加入暂存区 |
| git add . | &radic; | &radic; | &radic; | 将所有工作区文件加入暂存区 |
| git add -u | X | &radic; | &radic; | 将工作区除新创建文件外所有文件(Tracked)加入暂存区 |
| git add --ignore-removal . | &radic; | X | &radic; | 将工作区除已删除文件外所有文件加入暂存区 |

### git rm
```
	git rm -f test.txt # 这里做了两件事，将名为test.txt的文件有tracked状态改为untracked状态，即从版本库中删除；将test.txt从工作区删除
	# 以下三条命令等效于上条命令
	rm test.txt
	git add .
	git commit -m xxx
	
	git rm --cached test.txt # 这里只把名为test.txt的文件由tracked状态改为untracked状态，并且能够保留处于` staged `状态文件的内容
```