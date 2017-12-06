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
# 分支创建
```