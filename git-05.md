# Git-5
### 添加远程库
先有本地仓库，在服务器创建一个远程仓库，关联远程仓库
```
	git remote add origin git@server-name:path/repo-name.git
```
再关联远程分支
```
	git push -u origin master #origin远程库master分支，-u参数第一次使用，后面可以省略，关联本地master分支和远程master分支
```

先有远程仓库
```
	git clone git@github.com:michaelliao/gitskills.git
```
### 分支的创建与合并
```
# 分支查看
	git branch # *号表示当前所在分支
# 分支创建
	git branch name
# 分支切换
	git checkout name
# 分支切换+创建
	git checkout -b name
# 分支合并
	git merge name 
	# Fast Forward:直接将当前分支指向需要合并的另一个分支
	git merge --no-ff name -m xxx # 禁用Fast Forward 模式，会在合并的时候产生一个新的提交，需要带-m参数说明这次提交
# 分支删除
	git branch -d name
```

### 分支冲突解决
```
			* master
				|
				|---*feature
				|	    |
				|	    * add readme.txt
				|	    |
  add readme.txt*	    |
  				|	    |
  				*--------  merge conflict #只能手动修改
  				|
```

### Bug分支
```
	git stash #保存当前工作区以及Index数据
	
```