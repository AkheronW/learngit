# Git-6
### 多人协作开发
#### 查看远程库信息
```
	git remote
	git remote -v # 显示更详细的信息
```
#### 本地仓库分支推送到远程仓库分支
```
	git push origin <branch name>
```
#### 远程仓库克隆至本地，抓取远程分支
> 远程仓库克隆至本地后，` git branch `只有` master `分支
```
	# 将远程库dev分支创建至本地
	git checkout -b dev origin/dev
```

#### 更新本地分支或远程库分支
```
	#建立分支关联
	git branch --set-upstream-to=origin/<branch> <local>
	git pull #更新本地分支
	git push #更新远程分支
```

*如果同一个文件在多个本地库同时改动，在更新远程库时需要先更新本地仓库，手动解决冲突，再更新远程仓库。*